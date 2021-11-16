
# Data Visualization 

## Matplotlib Tutorial 

### What is matplotlib ? 

***matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats. We are going to explore matplotlib in interactive mode covering most common cases.*** 

* IPython and the pylab mode

*IPython is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands, improved debugging and much more.*

* pyplot 

*pyplot provides a convenient interface to the matplotlib object-oriented plotting library. It is modeled closely after Matlab(TM). Therefore, the majority of plotting commands in pyplot have Matlab(TM) analogs with similar arguments.*

### Simple plot 

* Changing colors and line widths 

        plt.figure(figsize=(10,6), dpi=80)
        plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
        plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")


* Setting limits 

        plt.xlim(X.min()*1.1, X.max()*1.1)
        plt.ylim(C.min()*1.1, C.max()*1.1)


* Setting ticks

        plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
        plt.yticks([-1, 0, +1]) 


* Setting tick labels 

        plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
            [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$'])

        plt.yticks([-1, 0, +1],
            [r'$-1$', r'$0$', r'$+1$'])


* Moving spines

        ax = plt.gca()
        ax.spines['right'].set_color('none')
        ax.spines['top'].set_color('none')
        ax.xaxis.set_ticks_position('bottom')
        ax.spines['bottom'].set_position(('data',0))
        ax.yaxis.set_ticks_position('left')
        ax.spines['left'].set_position(('data',0))


* Devil is in the details 

        for label in ax.get_xticklabels() + ax.get_yticklabels():
            label.set_fontsize(16)
            label.set_bbox(dict(facecolor='white', edgecolor='None', alpha=0.65 ))


### Figures, Subplots, Axes and Ticks 

> Figures 

**A figure is the windows in the GUI that has "Figure #" as title. Figures are numbered starting from 1 as opposed to the normal Python way starting from 0. This is clearly MATLAB-style.** 

> Subplots

**With subplot you can arrange plots in a regular grid. You need to specify the number of rows and columns and the number of the plot.**

> Axes 

**Axes are very similar to subplots but allow placement of plots at any location in the figure. So if we want to put a smaller plot inside a bigger one we do so with axes.** 

> Ticks 

**Well formatted ticks are an important part of publishing-ready figures. Matplotlib provides a totally configurable system for ticks. There are tick locators to specify where ticks should appear and tick formatters to give ticks the appearance you want. Major and minor ticks can be located and formatted independently from each other. By default minor ticks are not shown**

### Animation 

***The most easy way to make an animation in matplotlib is to declare a FuncAnimation object that specifies to matplotlib what is the figure to update, what is the update function and what is the delay between frames.***
