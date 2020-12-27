# CustomizedBarbs

A customized wind barbs class to modify the 
default matplotlib weak wind circle into bald barb


## Usage

1. You can use method `barbs` in module `customized_barbs.py`
to replace `plt.barbs` , the first parameter must be `Axes` instance.
2. use a specific parameter value `fill_empty='barb'` in `barbs` call

## Example

Here is an example,

```python
    import numpy as np
    import matplotlib.pyplot as plt
    from customized_barbs import barbs

    fig = plt.figure()
    ax = fig.add_subplot(111)
    plt.axis([0, 1, 0, 1])
    
    # make some artificial u-v wind data 
    x = np.array([0.2, 0.6,  0.5, 0.4, 0.8, ])
    y = np.array([0.2, 0.5, 0.4, 0.8, 0.8, ])
    u = np.array([0.5, 5, 10, 25, 0.1, ])
    v = np.array([0.5, 2.5, 2, 36, 0.1])
    
    # we dot the (x, y) position
    plt.plot(x, y, 'ko', markersize=2)
    # Here we set parameter fill_empty='barb' to enable the weak wind barb function
    # Please pay more attention to the first parameter, it must be axes instance
    barbs(ax, x, y, u, v, length=8, linewidth=0.5, fill_empty='barb',
          barb_increments={'half': 2, 'full': 4, 'flag': 20})

    plt.title("Bald barbs for weak wind speed")
    plt.show()
```


![image](https://github.com/wqshen/CustomizedBarbs/blob/master/example.png)