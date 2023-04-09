---
title: Interactive Plot in Jupyter
date: 2023-04-05
author: bosonicli
tags:
-   MehrWert
---

Assume I want to plot \\( f(x) = a sin(x) + b cos(x) \\) interactively in a Jupyter notebook, the easist way is to plot \\( f \\) directly with two slider widgets


```python

%matplotlib widget
import ipywidgets as widgets
from IPython.display import display
import matplotlib.pyplot as plt
import numpy as np

# Define the x range and the function to plot
def f(a, b):
    return a*np.sin(x) + b*np.cos(x)
x = np.linspace(0, 10, 100)

# Define the widgets
a_slider = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='a')
b_slider = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='b')
output_widget = widgets.Output()

# Define the function to update the plot
def update_plot(change):
    with output_widget:
        output_widget.clear_output(wait=True)
        plt.plot(x, f(a_slider.value, b_slider.value))
        plt.xlabel('x')
        plt.ylabel('y')
        plt.title('a*sin(x)+b*cos(x)')

# Register the update_plot function with the sliders
a_slider.observe(update_plot, names='value')
b_slider.observe(update_plot, names='value')

# Display the widgets
display(widgets.VBox([a_slider, b_slider, output_widget]))

```


But what if the function itself is complicated? A solution of an Ordinary Differential Equation (ODE), or an energy band diagram of 2-D material?

In static plot, it is often useful to return a plot figure directly from the plotting function


```python
# interactive plot of the data

def plot_f(a, b):
    x = np.linspace(0, 10, 100)
    y = f(x)
    fig, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title('Sum of sin and cosine')
    ax.set_xlabel('x')
    ax.set_ylabel('y')
    return fig

a_widget = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='a')
b_widget = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='b')
plot_widget = widgets.Checkbox(value=True, description='Show plot')

input_widgets = widgets.VBox([a_widget, b_widget, plot_widget])
output_widget = widgets.Output()

def on_value_change(change):
    if plot_widget.value:
        with output_widget:
            output_widget.clear_output(wait=True)
            fig = plot_f(a_widget.value, b_widget.value)
            display(fig)
            # Important! Explain later.
            # plt.close()

a_widget.observe(on_value_change, names='value')
b_widget.observe(on_value_change, names='value')
plot_widget.observe(on_value_change, names='value')

display(widgets.VBox([input_widgets, output_widget]))

```


It is also very useful to use the `interactive_output()` method to replace the manual `observe()` codes

```python
# create the output widget
output_widget = widgets.Output()

# create the interactive output widget
interactive_output_widget = widgets.interactive_output(
    plot_f, {'a': a_slider, 'b': b_slider})

# display the widgets
display(widgets.VBox([a_slider, b_slider, output_widget]))
output_widget.append_display_data(interactive_output_widget)
```

However, if you run these two codes in Jupyter notebook, an annoying problem may occur:

>   Everytime you make a change to the parameter controllers (slider/button, etc.) , and thus the interactive plot figure, the former figure stays in the notebook, and thus creating duplicate/afterimage of the figure.

The reason of this problem might be as follows:

>   Everytime parameters, and thus the fig changes, actually a new fig is generated, and the `plt()` module assigns its atrtrbute to the new fig. However, the former figs are not cleared. Even if you call `clear_output()`, the figs are just cleared from the `widgets.Output()` container, but still remain in the `plt()` module. That's why the latest fig appears on the top, in the `widgets.Output()` container along with other widgets, and former figs appears on the bottom as a long tail. Actually, if you see these dupicate/afterimage, on the top is the `widgets.Output()` and the rest are all in `plt()` container.

I never understand `matplotlib` so that confused me for a long time.

So I found that using `interactive_output()` is not a good idea. It's more automatic, but less custom in exchange.

I'd rather prefer the `observe()` way. There's only 1 minor change to make: `plt.close()` the figs container in the `obser()` controll function. This will clear former figs when parameter adjustment is made

```python
def on_value_change(change):
    if plot_widget.value:
        with output_widget:
            output_widget.clear_output(wait=True)
            fig = plot_f(a_widget.value, b_widget.value)
            display(fig)
            # That's what it does
            plt.close()
```

So the example code reads:

```python
# interactive plot of the data

%matplotlib widget
import ipywidgets as widgets
from IPython.display import display
import matplotlib.pyplot as plt
import numpy as np

# Define the x range and the function to plot
def f(a, b):
    return a*np.sin(x) + b*np.cos(x)

def plot_f(a, b):
    x = np.linspace(0, 10, 100)
    y = f(x)
    fig, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title('Sum of sin and cosine')
    ax.set_xlabel('x')
    ax.set_ylabel('y')
    return fig

a_widget = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='a')
b_widget = widgets.FloatSlider(min=-5, max=5, step=0.1, value=1.0, description='b')
plot_widget = widgets.Checkbox(value=True, description='Show plot')

input_widgets = widgets.VBox([a_widget, b_widget, plot_widget])
output_widget = widgets.Output()

def on_value_change(change):
    if plot_widget.value:
        with output_widget:
            output_widget.clear_output(wait=True)
            fig = plot_f(a_widget.value, b_widget.value)
            display(fig)
            # Important! Explain later.
            # plt.close()

a_widget.observe(on_value_change, names='value')
b_widget.observe(on_value_change, names='value')
plot_widget.observe(on_value_change, names='value')

display(widgets.VBox([input_widgets, output_widget]))

```

This code runs well on `Python3.7`. I've tried on 3.9/3.10, but it's not working well. No idea about the reason.
