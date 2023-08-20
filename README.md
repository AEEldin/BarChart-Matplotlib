# Bar Chart Matplotlib

In this tutorial, we would like to create bar charts using Python's Matplotlib.



### Prepare the matplotlib library.

This tutorial is using Python version 3.8, as a very stable version. With a ready python on your computer, check the following commands:

> python3 --version

> pip3 --version

> pip3 install matplotlib


Create a .py file, import the library, and you can also check the version of the matplotlib library as follows:
```
import matplotlib                # first step is to import the library
print(matplotlib.__version__)    # let's first check the version used
```

The pyplot is a submodule we will use where most of the Matplotlib utilities exist

```
import matplotlib.pyplot as plt  # let's import such submodule with an alias of plt
```



### Part 1: Let's create a simple bar chart

With Pyplot, you can use the bar() function to draw bar graphs.

The bar() function accepts two inputs:
+ The first input is a list of the categories (the horizontal axis) 
+ The second input is the corresponding values (the vertical axis)

```
import matplotlib.pyplot as plt

categories = ["First", "Second", "Third", "Forth"]
values = [200, 150, 100, 250]

plt.bar(categories,values)
plt.show()
```

### Part 2: the chart can also be displayed horizontally instead

We can use barh() function instead to display the full chart horizontally

```
import matplotlib.pyplot as plt

categories = ["First", "Second", "Third", "Forth"]
values = [200, 150, 100, 250]

plt.barh(categories,values)
plt.show()
```


### Part 3: configuring the style of the displayed bars

Both bar() and barh() functions accept more inputs to configure the style

+ The first option is the color of the bars. The library supports a wide range of colors and Hexadecimal color values that can be considered according to the application.

```
plt.bar(categories, values, color = "green")
plt.show()
```

You can also assign a color for each bar

```
displayColors = ['gray', 'green', 'gray', 'red']

plt.bar(categories, values, color = displayColors)
plt.show()
```





+ The second option is the width of the bars (in case of bar function) or the height of the bars (in case of barh function):

```
plt.bar(categories, values, width = 0.3)
plt.show()

plt.barh(categories,values, height = 0.8)
plt.show()
```




### Part 4: let's add some information (e.g., titles, labels) to the chart

```
import matplotlib.pyplot as plt

categories = ["First", "Second", "Third", "Forth"]
values = [200, 150, 100, 250]

plt.bar(categories, values, color = "red", width = 0.7)

font1 = {'family':'serif','color':'blue','size':12}             # let's define one formate
font2 = {'family':'serif','color':'red','size':10}              # let's define another formate

plt.title("Simple Plot", fontdict = font1, loc = 'center')      # let's include a title
plt.ylabel("Values", fontdict = font2)                          # let's include a label on the vertical axis
plt.xlabel("Categories", fontdict = font2)                      # let's include a label on the horizonatal axis

plt.show()

```


### Part5: displaying more than one plot

The subplot() function enables multiple plots to be displayed in the layout of the output figure; the layout is arranged in a table format with rows and columns.

The subplot() function accepts three parameters to describe the layout.

The first argument represents the number of rows
The second argument represents the number of columns
The third argument represents the position in the layout


```
import matplotlib.pyplot as plt

categories1 = ["First", "Second", "Third", "Forth"]
values1 = [200, 150, 100, 250]
plt.subplot(1, 2, 1)                #the layout is 1 row, 2 columns, and this plot is in the first position
plt.bar(categories1, values1, color = "red", width = 0.7)
plt.title("First plot")             #a title for this plot   
plt.ylabel("first y-axis")        
plt.xlabel("first x-axis") 


categories1 = ["First", "Second", "Third", "Forth"]
values1 = [200, 150, 100, 250]
plt.subplot(1, 2, 2)                #the layout is 1 row, 2 columns, and this plot is in the second position
plt.bar(categories1, values1, color = "green", width = 0.4)
plt.title("Second plot")            #a title for this plot
plt.ylabel("second y-axis")        
plt.xlabel("second x-axis") 

plt.suptitle("All plots")           #add one title on the collection
plt.show()
```
