# Data Visualization with Python
## Module 1 : Introduction to Data Visualization Tools
### 1.1 Introduction to Data Visualization
Why Build Visual?
For exploratory data analysis
Communicate data clearly
Share unbiased represantation of data
Use them to supoort recommendation to other decision makers.

Best practices:
- Less is more effective
- Less is more attractive
- Less is more impactive

Pie charts have recently come under fire from data visualization experts who argue that they are relevant only in the rarest of circumstances.

Bar graphs and charts on the other hand are argued to be far superior ways to quickly get a message across.

### 1.2 Introduction to Matplotlib
It was created by John Hunter, who was a neurobiologist and was part of a research team that was working on analyzing Electrocorticography
signals, ECoG for short.

Matplotlib's architecture is composed of three main layers: 
- the back-end layer
- the artist layer where much of the heavy lifting happens and is usually the appropriate programming paradigm when writing a web application server, or a UI application, or perhaps a script to be shared with other developers 
- scripting layer, which is the appropriate layer for everyday purposes and is considered a lighter scripting interface to simplify common tasks and for a quick and easy generation of graphics and plots.

### 1.3 Basic Plotting with Matplotlib

If the plot gets generated in a new
window then you can enforce generating plots within the browser using what's
called a magic function. A magic function starts with % Matplotlib, and to enforce
plots to be rendered within the browser, you pass in inline as the backend.

pandas also has a built-in implementation of matplotlib

df.plot(kind"line")
df["Column"].plot(kind="hist")

### 1.4 Line Plots
A line plot shows information that changes continuously with time. Here the data points are connected by straight lines. Line plots are also plotted on a two dimensional plane like scatter plots. Using line plots, we can create exciting visualizations to illustrate:
Annual revenue growth
Stock Market analysis over time
Product Sales over time

example:
years = list(map(str. range(1980,2014)))
df.loc['Haiti', years].plot(kind='line')
plt.show()

## Module 2 : Basic and Specialized Visualization Tools
Basic Visualization Tools
### 2.1 Area Plots
A type of plot that depicts accumulated totals using numbers or percentages over time.

Based on the line plot and is commonly used when trying to compare two or more quantities.

df.plot(kind="area")

### 2.2 Histograms
A histogram is used to represent continuous data in the form of bar. Each bar has discrete values in bar graphs, whereas in histograms, we have bars representing a range of values. Histograms show frequency distributions. We can use histograms to visualize:
- Students marks distribution
- Frequency of waiting time of customers in a Bank

df.plot(kind="hist")

e.g we're interested in visualizing the distribution of immigrants to Canada in the year 2013.

### 2.3 Bar Charts
A bar plot represents categorical data in rectangular bars. Each category is defined on one axis, and the value counts for this category are represented on another axis. Bar charts are generally used to compare values.We can use bar plots in visualizing:
- Pizza delivery time in peak and non peak hours
- Population comparison by gender
- Number of views by movie name

e.g say we're interested in visualizing in a discrete fashion how immigration from Iceland to Canada looked like from 1980 to 2013.

Specialized Visualization Tools
### 2.4 Pie Charts
A pie plot is a circle chart mainly used to represent proportion of part of given data with respect to the whole data. Each slice represents a proportion and on total of the proportion becomes a whole. We can use bar plots in visualizing:
- Sales turnover percentatge with respect to different products
- Monthly expenditure of a Family

### 2.5 Box Plots
A boxplot is a way of statistically representing the distribution of given data through 5 main dimensions.

The first dimension is minimum, which is the smallest number in the sorted data.
Its value can be obtained by subtracting 1.5 times the IQR where IQR is interquartile range
from the first quartile.

The second dimension is first quartile which is 25% of the way through the sorted data.
In other words, 1/4 of the data points are less than this value.

The third dimension is median, which is the median of the sorted data.

The fourth dimension is third quartile, which is 75% of the way through the sorted data.
In other words, 3/4 of the data points are less than this value.

And the final dimension is maximum, which is the highest number in the sorted data where
maximum equals third quartile summed with 1.5 multiplied by IQR.

Finally, boxplots also display outliers as individual dots that occur outside the upper
and lower extremes.

### 2.7 Scatter Plot
A scatter plot shows the relationship between 2 variables on the x and y-axis. The data points here appear scattered when plotted on a two-dimensional plane. Using scatter plots, we can create exciting visualizations to express various relationships, such as:
- Height vs weight of persons
- Engine size vs automobile price
- Exercise time vs Body Fat

### 2.8 Bubble Plot
A bubble plot is used to show the relationship between 3 or more variables. It is an extension of a scatter plot. Bubble plots are ideal for visualizing:
- Global Economic position of Industries
- Impact of viruses on Diseases

## Module 3 : Advanced Visualization Tools
### 3.1 Waffle Charts
A waffle chart is a great way to visualize data in relation to a whole or to highlight progress against a given threshold.

The main idea here is for a given waffle chart whose desired height and width are defined, the contribution of each country is transformed into a number of tiles that is proportional to the country's contribution to the total, so that more the contribution the more the tiles, resulting in what resembles a waffle when combined. Hence the name waffle chart.

### 3.2 Word Clouds
A word cloud is simply a depiction of the
importance of different words in the body of text. A word cloud works in a simple way; the more a specific word appears in a source of textual data the bigger and bolder it appears in the world cloud.

### 3.2 Seaborn and Regression Plots
Seaborn is another data visualization library, it is actually based on Matplotlib. It was built primarily to provide a high-level interface for drawing
attractive statistical graphics, such as regression plots, box plots, and so on. Seaborn makes creating plots very efficient. Therefore with Seaborn you can generate plots with code that is 5 times less than with Matplotlib.

Visualizing Geospatial Data 
### 3.3 Introduction to Folium
Folium is a powerful data visualization library in
Python that was built primarily to help people visualize geospatial data. 

With Folium, you can create a map of any location in the world as long as you know its latitude and longitude values. 

You can also create a map and superimpose markers as well as clusters of markers on top of the map for cool and very interesting visualizations. 

You can also create maps of different styles such as street level map, stamen map, and a couple others.

The default map style is the open street map, which shows a street view of an area when you're zoomed in and shows the borders of the world countries when you're zoomed all the way out.

Tiles parameter:
- Stamen toner map: great for visualizing and exploring river meanders and coastal zones.
- Stamen terrain: great for visualizing hill shading and natural vegetations colours.

### 3.4 Maps with Markers
To add a circular mark on map, create a feature group. Create a child in the form of a circular mark. Specify the location of the child by passing in its latitude and longitude values. And once we're done adding children to the feature group, we add the featured group to the map. And there you have it.

### 3.5 Choropleth Maps
A choropleth map is a thematic map in which areas are shaded or patterned in proportion to the measurement of the statistical variable being displayed on the map, such as population density or per capita income.

Folium requires a Geo JSON file that includes geospatial data of the region. For a choropleth map of the world, we would need a Geo JSON file that lists each country along with any geospatial data to define its borders and boundaries.

## Module 4 : Creating Dashboards with Plotly and Dash
### 4.1 Dashboarding Overview
With real-time visuals on the dashboard, understanding business moving parts becomes easy.
Based on the report type and data, suitable graphs and charts can be created in one central location.  This provides an easy way for stakeholders to understand what is going right, wrong, and what needs to be improved. Getting the big-picture in one place can help businesses make informed decisions. This improves business performance. In general, the best dashboards answer critical business questions.

Web-based dashboarding tool options available in Python:
Dash is a python framework for building web analytic applications. It is written on top of Flask, Plotly.js, and React.js. Dash is well-suited for building data visualization apps with highly custom user interfaces.
Panel works with visualizations from Bokeh, Matplotlib, HoloViews, and many other Python plotting libraries, making them instantly viewable either individually or when combined with interactive widgets that control them. 
Voilà turns Jupyter notebooks into standalone web applications. It can be used with separate layout tools like jupyter-flex or templates like voila-vuetify.
Streamlit can easily turn data scripts into shareable web apps with 3 main principles: embrace python scripting, treat widgets as variables, and reuse data and computation.
Bokeh is a plotting library, a widget and app library. It acts as a server for both plots and dashboards.
Bowtie allows users to build dashboards in pure Python.

For more information about Dashboards, visit the following links:
- [Python dashboarding tools](https://pyviz.org/dashboarding/)
- [John Snow's data journalism](https://www.theguardian.com/news/datablog/2013/mar/15/john-snow-cholera-map)

### 4.2 Introduction to Plotly
Plotly is an interactive, open source plotting library that supports over 40 unique chart types. It is available in Python, R and Javascript.
Plotly python is build on top of Plotly Javascript library and includes chart types like statistical, financial, maps, scientific, and 3-dimensional data .

The web based visualizations created using Plotly python can be displayed in Jupyter notebook, saved to standalone HTML files, or served as part of pure Python-built web applications using Dash.

Two Plotly sub-modules:
- Plotly Graph Objects
- Plotly Express

Plotly Graph Objects: This is a low level interface to figures, traces and layout. The Plotly graph objects module provides an automatically generated hierarchy of classes ( figures, traces, and layout) called graph objects. These graph objects represent figures with a top-level class plotly.graph_objects.Figure.

Plotly Express: Plotly express is a high-level wrapper for Plotly. It is a recommended starting point for creating the most common figures provided by Plotly using a simpler syntax. It uses graph objects internally. Now let us use these libraries to plot some charts We will start with plotly_graph_objects to plot line and scatter plots

To learn more about using Plotly to create dashboards, explore:

- [Plotly python](https://plotly.com/python/getting-started/)
- [Plotly graph objects with example](https://plotly.com/python/graph-objects/)
- [Plotly express](https://plotly.com/python/plotly-express/)
- [API reference](https://plotly.com/python-api-reference/)

Here are additional useful resources:

- [Plotly cheatsheet](https://images.plot.ly/plotly-documentation/images/plotly_js_cheat_sheet.pdf)
- [Plotly community](https://community.plotly.com/c/api/5)
- [Related blogs](https://plotlygraphs.medium.com/)
- [Open-source datasets](https://developer.ibm.com/exchanges/data/)


### 4.3 Introduction to Dash
Dash is a Open-Source User Interface Python library for creating reactive, web-based applications. It is enterprise-ready and a first-class member of Plotly’s open-source tools.

Dash applications are web servers running Flask and communicating JSON packets over HTTP requests.

Dash’s frontend renders components using React.js. It is easy to build a Graphical User Interface using dash as it abstracts all technologies required to build the applications.

Dash is Declarative and Reactive. Dash output can be rendered in web browser and can be deployed to servers. 

Dash uses a simple reactive decorator
for binding code to the UI. This is inherently mobile and cross-platform ready.

What to do:
- Determine the layout of the application.
- Add interactivity to the application.

To learn more about Dash, explore:
- [Complete dash user guide](https://dash.plotly.com/) 
- [Dash core components](https://dash.plotly.com/dash-core-components) 
- [Dash HTML components](https://dash.plotly.com/dash-html-components) 
- [Dash community forum](https://community.plotly.com/c/python/25) 
- [Dash community forum](https://medium.com/plotly/tagged/dash) 


### 4.4 Make Dashboards Interactive
Connect core and HTML components using callbacks.

A callback function is a python function that is
automatically called by Dash whenever an input component's property changes.

Callback function is decorated with @app.callback` decorator.

In Python, @app.callback is a decorator used in the Dash framework to specify that a function should be called when an input component changes its value.The Input and Output functions are used to define the inputs and outputs of a callback function.

Steps:
- Define the callback decorator
- Define the callback function that uses the input provided to perform the computation
- Create graph and return it as an output

To learn more about making interactive dashboards in Dash, visit:

- [Python decorators reference 1](https://realpython.com/primer-on-python-decorators/)
- [Python decorators reference 2](https://www.python.org/dev/peps/pep-0318/#current-syntax)
- [Callbacks with example](https://dash.plotly.com/basic-callbacks)
- [Dash app gallery](https://dash-gallery.plotly.host/Portal/)
- [Dash community components](https://plotly.com/dash-community-components/)

4.5 Module 4 Lesson Summary
- Best dashboards answer critical business questions. It will help business make informed decisions, thereby improving performance.   
- Dashboards can produce real-time visuals. 
- Plotly is an interactive, open-source plotting library that supports over 40 chart types.   
- The web based visualizations created using Plotly python can be displayed in Jupyter notebook, saved to standalone HTML files, or served as part of pure Python-built web applications using Dash.   
- Plotly Graph Objects is the low-level interface to figures, traces, and layout whereas plotly express is a high-level wrapper for Plotly.   
- Dash is an Open-Source User Interface Python library for creating reactive, web-based applications. It is both enterprise-ready and a first-class member of Plotly’s open-source tools.  
- Core and HTML are the two components of dash.   
- The dash_html_components library has a component for every HTML tag.   
- The dash_core_components describe higher-level components that are interactive and are generated with JavaScript, HTML, and CSS through the React.js library.   
- A callback function is a python function that is automatically called by Dash whenever an input component's property changes. Callback function is decorated with `@app.callback` decorator.   
- Callback decorator function takes two parameters: Input and Output. Input and Output to the callback function will have component id and component property. Multiple inputs or outputs should be enclosed inside either a list or tuple.
