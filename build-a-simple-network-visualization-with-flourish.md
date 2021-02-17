# Build a simple network visualization with Flourish

As we have learned, network analysis is a whole field whose founding premise is that one can glean critical and revealing information from the ways that entities connect with each other. Part of the network analysis process includes running fairly sophisticated algorithmic measures of various properties of network graphs and their nodes and links.

But sometimes you just want to see how your entities connect, in an easy-to-interpret, visual diagram. [Flourish](https://flourish.studio/), the web-based data-visualization package, has some nice templates for that, and today we'll learn to use them. 

At the end of this tutorial, you'll find links to resources you can use to expand your knowledge of network analysis and visualization

## 1. Download your dataset

We'll use a dataset that comes courtesy of [Valdis Krebs](http://www.orgnet.com/divided2.html), via a [dataset collection assembled by Melanie Walsh](https://github.com/melaniewalsh/sample-social-network-datasets). The dataset is a list of political books published in 2004, categorized by their political orientation. Two books are connected in Krebs's edgelist when a purchaser bought them together.

**Please download the zipped file of the datasets **[**here**](https://www.dropbox.com/s/66mrch9kj791hv6/political-books-dataset.zip?dl=0)**, and then decompress them.**.

![][1]

[1]: images/build-a-simple-network-visualization-with-flourish/download-your-dataset.png

## 2. Sign into Flourish and create a new visualization

Go to the [Flourish homepage](https://flourish.studio/), create an account if you don't already have one, and sign in. Then press **New Visualization.**

![][2]

[2]: images/build-a-simple-network-visualization-with-flourish/sign-into-flourish-and-create-a-new-visualization.png

## 3. Find the Directional graph template

You'll have to scroll about three-fourths of the way down the page to find the **Network graph **templates. (A good chance to familiarize yourself with some of the Flourish visualizations!) Once you're there, click on the **Directional graph** template button.

![][3]

[3]: images/build-a-simple-network-visualization-with-flourish/find-the-directional-graph-template.png

## 4. Getting (re)acquainted with the interface

You may recall that Flourish templates come pre-loaded with sample data. The idea is that you use that data as a guide to setting up your own properly. Click on the **Data** tab to view the prepopulated data.

![][4]

[4]: images/build-a-simple-network-visualization-with-flourish/getting--re-acquainted-with-the-interface.png

## 5. Understanding network data

You'll notice that the network graph data includes two tabs: one called **Links** and one called **Points**. **Links** is an edge list, just with a different name: it includes two columns, showing how the nodes are connected.

**Points** is a node list: a list of every node included in the network graph. You don't need to have a node list (since all of the nodes are included in the edge list, but there are good reasons you might want to. In this case, the node list supplies not only the names of each node (in column **A**), but also attributes of those nodes (in column **B**). You can use these attributes to add information to your visualization.

![][5]

[5]: images/build-a-simple-network-visualization-with-flourish/understanding-network-data.png

## 6. Load your data (1)

We'll start by adding our **Points** data. Press **Upload data** and then choose **political-books-data.csv**. You'll next be asked to **select the columns**. 

Our points data is similar to the data we started with, in that it has two colum .>ns. The first, **id**, is a list of all the books included in our network. The second, **political_ideology**, tells you how these books have been categorized: as neutral, conservative, or liberal.

On the right side of the screen, we'll tell Flourish which column to use for what. As with the first dataset, we'll use column **A** for the id of each node. Column **B** serves a different function, though. While the last dataset provided numerical information about each node, ours provides categorical information. So instead of using column **B** to encode the size of our nodes, we'll use it as a way to group the nodes.

So for **id**, select column **A**, and for **Group**, select column **B**. The others you can leave blank.

(Someday you might be interested to know that you could replace Flourish's circles with your own custom images, using the **Image** column, and provide custom info for popup labels using the **Info for popups** option.)



![][6]

[6]: images/build-a-simple-network-visualization-with-flourish/load-your-data--1-.png

## 7. Load your data (2)

Let's consider the **Links** tab now. Click on **Upload data** and replace Flourish's data with **political-books-edges.csv**. Our columns are similar: column **A** is our **Source** and column **B **is our **Target**. 

You'll notice, though, that we have a **Weight** column, column **C**. Remember, in network analysis "weight" refers to the strength of a connection — in this case, the number of times each pair of books was purchased together. So enter **C** for **Value of link**.

![][7]

[7]: images/build-a-simple-network-visualization-with-flourish/load-your-data--2-.png

## 8. Examine your network graph

Click on the **Preview** tab to see what you've done. You did it, you made a network graph! You'll find that hovering over each node reveals its name, and that the nodes are colored to indicate political belief: green for liberal, yellow for conservative, blue for neutral.

There are a few things I don't like so much, though. Let's start with the edges, or "links," They're depicted here as arrows, which would make sense if this were a directed graph. But this is an *undirected* graph: if book a is purchased with book b, than book b is necessarily purchased with book a.

Let's get rid of those arrows. On the right-hand panel, expand the **Links** section. You'll see a switch labeled **Show arrows on links. **Go ahead and turn that switch off.



![][8]

[8]: images/build-a-simple-network-visualization-with-flourish/examine-your-network-graph.png

## 9. Neaten those edges

Your graph is set to thicken the links between nodes when the weight of an edge increases. Those links are looking really thick, though. Inspecting the data for **Links** reveals why: the weight of every link is actually 1. Yet if we check the links section of the **Preview** tab, we can see that the **Maximum width** of the links is set to 10. That's too wide! 

Change the maximum width to 1, and your graph will look a lot neater!

![][9]

[9]: images/build-a-simple-network-visualization-with-flourish/neaten-those-edges.png

## 10. Experiment with settings

Those few adjustments take care of the major settings for your diagram. Not too hard, huh? The main thing, as with all Flourish data visualizations, is that you have to import your data all set to go; you can't really manipulate it once it's imported.

There are a few other fun settings that might interest you. Try:

* Turning on animations (**Animations → Animate network simulation**)
* Increasing the repulsion between points (**Advanced → Repulsion between points**)
* Giving your network a title (**Header** → **Title**)
* Filling in the information about the data source: (**Footer** → **Text**). The **source name** is Valdis Krebs, and the **source URL** is [http://www.orgnet.com/divided2.html.](http://www.orgnet.com/divided2.html) 
* Enabling popups (**Popups** → **Enabled**)

![][10]

[10]: images/build-a-simple-network-visualization-with-flourish/experiment-with-settings.png

## 11. Some closing notes

1. I think our network graph looks pretty good! Once you embed it in another website, viewers will be able to explore it by clicking on points and dragging them around. 

Still, there are some definite limits to the network visualization Flourish offers.

1. There's no provision for encoding any kind of centrality, or for calculating any complext network attributes. (You could include a column that provides centrality measures, and use that to size the points, but Flourish won't calculate that for you.)
1. Flourish doesn't distinguish between **id** and **label**, so if you've been using a unique id to refer to each of your points, you may encounter some confusion if some of your labels share a name.
1. You can't include a filter function in your diagram, or a search function.

Thus, it might be most accurate to say that Flourish network visualizations are most useful for offering a visual method for exploring a network dataset, rather than demonstrating a point with a network.

If you'd like to incorporate more complicated measures and calculations in your network analysis, you'll need to use a different software package. [**Cytoscape**](https://cytoscape.org/) is a software package designed for more sophisticated, complex analysis of network data, and while it does have a bit of a learning curve, it includes a huge array of calculations and filtering mechanisms. I have an extensive tutorial [here](https://github.com/miriamposner/cytoscape_tutorials), which you are welcome to use.

Should you want to offer your viewers a network diagram with more bells and whistles, such as dynamic filtering and a search function, you may want to explore the capacities of [**D3**](https://d3js.org/), the Javascript library that is the basis for the network visualization included with Flourish. Here is a [gallery](http://coppelia.io/2014/07/an-a-to-z-of-extra-features-for-the-d3-force-layout/) of additional features you can incorporate into a D3 graph. You will need to learn a little bit about D3, however.

![][11]

[11]: images/build-a-simple-network-visualization-with-flourish/some-closing-notes.png

## 12. What would you like to do now?

You have a few options, now that you've learned how to create a basic network visualization. You can:

1. [Get started on your homework](http://miriamposner.com/classes/dh201w21/other-assignments/homework-7/).
1. [Learn about calculating more sophisticated measures with Cytoscape](https://github.com/miriamposner/cytoscape_tutorials).
1. Learn about customizing your network visualization with D3. (I find Scott Murray's book, [*Interactive Data Visualization for the Web*](https://learning.oreilly.com/library/view/interactive-data-visualization/9781491921296/), the most useful source for learning D3. You'll need to authenticate with a UCLA account in order to use this link.)
1. The [igraph package for the R programming language](https://igraph.org/r/) has a learning curve, but once you work out the kinks, you'll find that you can make calculations and work with data without quite so much fiddling with dials and buttons. [Jesse Sadler has an introductory tutorial for igraph](https://www.jessesadler.com/post/network-analysis-with-r/) which, while I have not walked through it myself, seems well-written and thorough.
1. Read Paula R. Curtis's [well-described narrative of a scholarly journey toward humanistic network analysis](http://prcurtis.com/DH/network_analysis/), and think about how it might apply to your own work.