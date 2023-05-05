Download Link: https://assignmentchef.com/product/solved-ece232ee-project-1-random-graphs-and-random-walks
<br>
One can use igraph library<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> to generate different networks and measure various properties of a given network. The library has R and Python implementations. You may choose either language that you prefer. However, for this project, using R is strongly recommended, as some functions might not be implemented for the Python version of the package.

Submission: Upload a zip file containing your report and codes to CCLE. One submission from any member of groups is sufficient.

<h2>1 Generating Random Networks</h2>

<ol>

 <li>Create random networks using Erdös-Rényi (ER) model

  <ul>

   <li>Create an undirected random networks with <em>n </em>= 1000 nodes, and the probability <em>p </em>for drawing an edge between two arbitrary vertices 0.003, 0.004, 0.01, 0.05, and 0.1. Plot the degree distributions. What distribution is observed? Explain why. Also, report the mean and variance of the degree distributions and compare them to the theoretical values.</li>

   <li>For each <em>p </em>and <em>n </em>= 1000, answer the following questions: Are all random realizations of the ER network connected? Numerically estimate the probability that a generated network is connected. For one instance of the networks with that <em>p</em>, find the giant connected component (GCC) if not connected. What is the diameter of the GCC?</li>

   <li>It turns out that the normalized GCC size (i.e., the size of theGCC as a fraction of the total network size) is a highly nonlinear function of <em>p</em>, with interesting properties occurring for values where . For <em>n </em>= 1000, sweep over values of <em>p </em>in this region and create 100 random networks for each <em>p</em>. Then scatter plot the normalized GCC sizes vs <em>p</em>. Empirically estimate the value of <em>p </em>where a giant connected component starts to emerge (define your criterion of “emergence”)? Do they match with theoretical values mentioned or derived in lectures?</li>

   <li>Define the average degree of nodes <em>c </em>= <em>n </em>× <em>p </em>= 0<em>.</em>5. Sweep over number of nodes, <em>n</em>, ranging from 100 to 10000. Plot the expected size of the GCC of ER networks with <em>n </em>nodes and edge-formation probabilities <em>p </em>= <em>c/n</em>, as a function of <em>n</em>. What trend is observed? ii. Repeat the same for <em>c </em>= 1.</li>

  </ul></li>

</ol>

iii. Repeat the same for values of <em>c </em>= 1<em>.</em>1<em>,</em>1<em>.</em>2<em>,</em>1<em>.</em>3, and show the results for these three values in a single plot.

<ol start="2">

 <li>Create networks using preferential attachment model

  <ul>

   <li>Create an undirected network with <em>n </em>= 1000 nodes, with preferential attachment model, where each new node attaches to <em>m </em>= 1 old nodes. Is such a network always connected?</li>

   <li>Use fast greedy method to find the community structure. Measure modularity.</li>

   <li>Try to generate a larger network with 10000 nodes using thesame model. Compute modularity. How is it compared to the smaller network’s modularity?</li>

   <li>Plot the degree distribution in a log-log scale for both <em>n </em>= 1000<em>,</em>10000, then estimate the slope of the plot.</li>

   <li>You can randomly pick a node <em>i</em>, and then randomly pick a neighbor <em>j </em>of that node. Plot the degree distribution of nodes <em>j </em>that are picked with this process, in the log-log scale. How does this differ from the node degree distribution?</li>

   <li>Estimate the expected degree of a node that is added at timestep <em>i </em>for 1 ≤ <em>i </em>≤ 1000. Show the relationship between the age of nodes and their expected degree through an appropriate plot.</li>

   <li>Repeat the previous parts for <em>m </em>= 2<em>, </em>and <em>m </em>= 5. Why was modularity for <em>m </em>= 1 high?</li>

   <li>Again, generate a preferential attachment network with <em>n </em>= 1000, <em>m </em>= 1. Take its degree sequence and create a new network with the same degree sequence, through stub-matching procedure. Plot both networks, mark communities on their plots, and measure their modularity. Compare the two procedures for creating random power-law networks.</li>

  </ul></li>

 <li>Create a modified preferential attachment model that penalizesthe age of a node

  <ul>

   <li>Each time a new vertex is added, it creates <em>m </em>links to old vertices and the probability that an old vertex is cited depends on its degree (preferential attachment) and age. In particular, the probability that a newly added vertex connects to an old vertex is proportional to:</li>

  </ul></li>

</ol>

<em>P</em>[<em>i</em>] ∼ (<em>ck<sub>i</sub><sup>α </sup></em>+ <em>a</em>)(<em>dl<sub>i</sub><sup>β </sup></em>+ <em>b</em>)<em>,</em>

where <em>k<sub>i </sub></em>is the degree of vertex <em>i </em>in the current time step, and <em>l<sub>i </sub></em>is the age of vertex <em>i</em>. Produce such an undirected network with 1000 nodes and parameters <em>m </em>= 1, <em>α </em>= 1<em>,β </em>= −1, and <em>a </em>= <em>c </em>= <em>d </em>= 1<em>,b </em>= 0. Plot the degree distribution. What is the power law exponent?

<ul>

 <li>Use fast greedy method to find the community structure. Whatis the modularity?</li>

</ul>

<h2>2 Random Walk on Networks</h2>

<ol>

 <li>Random walk on Erdös-Rényi networks

  <ul>

   <li>Create an undirected random network with 1000 nodes, andthe probability <em>p </em>for drawing an edge between any pair of nodes equal to 0.01.</li>

   <li>Let a random walker start from a randomly selected node (noteleportation). We use <em>t </em>to denote the number of steps that the walker has taken. Measure the average distance (defined as the shortest path length) h<em>s</em>(<em>t</em>)i of the walker from his starting point at step <em>t</em>. Also, measure the standard deviation <em>σ</em><sup>2</sup>(<em>t</em>) = h(<em>s</em>(<em>t</em>) − h<em>s</em>(<em>t</em>)i)<sup>2</sup>i of this distance. Plot h<em>s</em>(<em>t</em>)i s. <em>t </em>and <em>σ</em><sup>2</sup>(<em>t</em>) v.s.</li>

  </ul></li>

</ol>

<ol>

 <li><em>t</em>. Here, the average h·i is over random choices of the starting nodes.</li>

</ol>

<ul>

 <li>Measure the degree distribution of the nodes reached at theend of the random walk. How does it compare to the degree distribution of graph?</li>

 <li>Repeat (b) for undirected random networks with 100 and 10000 nodes. Compare the results and explain qualitatively. Does the diameter of the network play a role?</li>

</ul>

<ol start="2">

 <li>Random walk on networks with fat-tailed degree distribution

  <ul>

   <li>Generate an undirected preferential attachment network with1000 nodes, where each new node attaches to <em>m </em>= 1 old nodes.</li>

   <li>Let a random walker start from a randomly selected node. Measure and plot h<em>s</em>(<em>t</em>)i s. <em>t </em>and <em>σ</em><sup>2</sup>(<em>t</em>) v.s. <em>t</em>.</li>

   <li>Measure the degree distribution of the nodes reached at theend of the random walk on this network. How does it compare with the degree distribution of the graph?</li>

   <li>Repeat (b) for preferential attachment networks with 100 and10000 nodes, and <em>m </em>= 1. Compare the results and explain qualitatively. Does the diameter of the network play a role?</li>

  </ul></li>

 <li>PageRank</li>

</ol>

The PageRank algorithm, as used by the Google search engine, exploits the linkage structure of the web to compute global “importance” scores that can be used to influence the ranking of search results. Here, we use random walk to simulate PageRank.

<ul>

 <li>Create a directed random network with 1000 nodes, using thepreferential attachment model, where <em>m </em>= 4. Note that in this directed model, the out-degree of every node is <em>m</em>, while the in-degrees follow a power law distribution. Measure the probability that the walker visits each node. Is this probability related to the degree of the nodes?</li>

 <li>In all previous questions, we didn’t have any teleportation.Now, we use a teleportation probability of <em>α </em>= 0<em>.</em>15. By performing random walks on the network created in 3(a), measure the probability that the walker visits each node. Is this probability related to the degree of the node?</li>

</ul>

<ol start="4">

 <li>Personalized PageRank</li>

</ol>

While the use of PageRank has proven very effective, the web’s rapid growth in size and diversity drives an increasing demand for greater flexibility in ranking. Ideally, each user should be able to define their own notion of importance for each individual query.

<ul>

 <li>Suppose you have your own notion of importance. Your interestin a node is proportional to the node’s PageRank, because you totally rely upon Google to decide which website to visit (assume that these nodes represent websites). Again, use random walk on network generated in part 3 to simulate this personalized PageRank. Here the teleportation probability to each node is proportional to its PageRank (as opposed to the regular PageRank, where at teleportation, the chance of visiting all nodes are the same and equal to ). Again, let the teleportation probability be equal to <em>α </em>= 0<em>.</em>15. Compare the results with</li>

</ul>

3(b).

<ul>

 <li>Find two nodes in the network with median PageRanks. Repeat part (a) if teleportations land only on those two nodes (with probabilities 1/2, 1/2). How are the PageRank values affected?</li>

 <li>More or less, (c) is what happens in the real world, in that auser browsing the web only teleports to a set of trusted web pages. However, this is against the different assumption of normal PageRank, where we assume that people’s interest in all nodes are the same. Can you take into account the effect of this self-reinforcement and adjust the PageRank equation?</li>

</ul>

<h2>Final Remarks</h2>

The following functions from igraph library are useful for this project:

<ul>

 <li>degree, degree.distribution, diameter, vcount, ecount</li>

 <li>graph.game, barabasi.game, aging.prefatt.game, degree.sequence.game</li>

 <li>page_rank</li>

</ul>

For part 2 of the project, you can start off with the Jupyter notebook provided to you.

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="http://igraph.sourceforge.net/">http://igraph.sourceforge.net/</a>