Download Link: https://assignmentchef.com/product/solved-comp9318-assignment-1
<br>



Consider the following base cuboid <em>Sales </em>with <em>four </em>tuples and the aggregate function SUM:

<table width="269">

 <tbody>

  <tr>

   <td width="79"><em>Location</em></td>

   <td width="46"><em>Time</em></td>

   <td width="74"><em>Item</em></td>

   <td width="71"><em>Quantity</em></td>

  </tr>

  <tr>

   <td width="79">Sydney</td>

   <td width="46">2005</td>

   <td width="74">PS2</td>

   <td width="71">1400</td>

  </tr>

  <tr>

   <td width="79">Sydney</td>

   <td width="46">2006</td>

   <td width="74">PS2</td>

   <td width="71">1500</td>

  </tr>

  <tr>

   <td width="79">Sydney</td>

   <td width="46">2006</td>

   <td width="74">Wii</td>

   <td width="71">500</td>

  </tr>

  <tr>

   <td width="79">Melbourne</td>

   <td width="46">2005</td>

   <td width="74">XBox 360</td>

   <td width="71">1700</td>

  </tr>

 </tbody>

</table>

<em>Location</em>, <em>Time</em>, and <em>Item </em>are dimensions and <em>Quantity </em>is the measure. Suppose the system has built-in support for the value <strong>ALL</strong>.

<ul>

 <li>List the tuples in the complete data cube of <em>R </em>in a tabular form with 4 attributes,</li>

</ul>

i.e., <em>Location,Time,Item,</em>SUM(<em>Quantity</em>)?

<ul>

 <li>Write down an equivalent SQL statement that computes the same result (i.e., the cube). You can <em>only </em>use standard SQL constructs, i.e., no <strong>CUBE BY </strong></li>

 <li>Consider the following <em>ice-berg cube </em>query:</li>

</ul>

SELECT Location, Time, Item, SUM(Quantity)

FROM          Sales

CUBE BY Location, Time, Item HAVING COUNT(*) &gt; 1

Draw the result of the query in a tabular form.

<ul>

 <li>Assume that we adopt a MOLAP architecture to store the full data cube of <em>R</em>, with the following mapping functions:</li>

</ul>

= ‘Sydney’<em>, </em>= ‘Melbourne’<em>,</em>

<sup></sup>0      if <em>x </em>= <strong>ALL</strong><em>.</em>

<table width="185">

 <tbody>

  <tr>

   <td width="109"></td>

   <td width="76">if <em>x </em>= 2005<em>, </em>if <em>x </em>= 2006<em>,</em></td>

  </tr>

 </tbody>

</table>

0      if <em>x </em>= <strong>ALL</strong><em>.</em>

1        if <em>x </em>= ‘PS2’<em>,</em>

<table width="224">

 <tbody>

  <tr>

   <td width="107">2<em>f<sub>Item</sub></em>(<em>x</em>) =30</td>

   <td width="117">if <em>x </em>= ‘XBox 360’<em>, </em>if <em>x </em>= ‘Wii’<em>, </em>if <em>x </em>= <strong>ALL</strong><em>.</em></td>

  </tr>

 </tbody>

</table>

Draw the MOLAP cube (i.e., sparse multi-dimensional array) in a tabular form of (<em>ArrayIndex,V alue</em>). You also need to write down the function you chose to map a multi-dimensional point to a one-dimensioinal point.

Q2. (<em>30 marks</em>)

Consider the given <strong>similarity </strong>matrix. You are asked to perform group average hierarchical clustering on this dataset.

You need to show the steps and final result of the clustering algorithm. You will show the final results by drawing a dendrogram. The dendrogram should clearly show the order in which the points are merged.

<table width="168">

 <tbody>

  <tr>

   <td width="18"> </td>

   <td width="30"><em>p</em><sub>1</sub></td>

   <td width="30"><em>p</em><sub>2</sub></td>

   <td width="30"><em>p</em><sub>3</sub></td>

   <td width="30"><em>p</em><sub>4</sub></td>

   <td width="30"><em>p</em><sub>5</sub></td>

  </tr>

  <tr>

   <td width="18"><em>p</em><sub>1</sub></td>

   <td width="30">1.00</td>

   <td width="30">0.10</td>

   <td width="30">0.41</td>

   <td width="30">0.55</td>

   <td width="30">0.35</td>

  </tr>

  <tr>

   <td width="18"><em>p</em><sub>2</sub></td>

   <td width="30">0.10</td>

   <td width="30">1.00</td>

   <td width="30">0.64</td>

   <td width="30">0.47</td>

   <td width="30">0.98</td>

  </tr>

  <tr>

   <td width="18"><em>p</em><sub>3</sub></td>

   <td width="30">0.41</td>

   <td width="30">0.64</td>

   <td width="30">1.00</td>

   <td width="30">0.44</td>

   <td width="30">0.85</td>

  </tr>

  <tr>

   <td width="18"><em>p</em><sub>4</sub></td>

   <td width="30">0.55</td>

   <td width="30">0.47</td>

   <td width="30">0.44</td>

   <td width="30">1.00</td>

   <td width="30">0.76</td>

  </tr>

  <tr>

   <td width="18"><em>p</em><sub>5</sub></td>

   <td width="30">0.35</td>

   <td width="30">0.98</td>

   <td width="30">0.85</td>

   <td width="30">0.76</td>

   <td width="30">1.00</td>

  </tr>

 </tbody>

</table>

Q3. (<em>30 marks</em>)

<strong>Algorithm 1: </strong><em>k</em>-means(<em>D</em>, <em>k</em>)

<strong>Data: </strong><em>D </em>is a dataset of <em>n d</em>-dimensional points; <em>k </em>is the number of clusters.

<strong>1 </strong>Initialize <em>k </em>centers <em>C </em>= [<em>c</em><sub>1</sub><em>,c</em><sub>2</sub><em>,…,c<sub>k</sub></em>];

Consider the (slightly incomplete) <em>k</em>-means clustering algorithm as depicted in Algorithm 1.

(1) Assume that the stopping criterion is till the algorithm converges to the final <em>k </em>clusters. Can you insert several lines of pseudo-code to the algorithm to implement this logic? You are <strong>not </strong>allowed to change the first 7 lines though. (2) The cost of <em>k </em>clusters is just the total cost of each group <em>g<sub>i</sub></em>, or formally

<em>k</em>

<em>cost</em>(<em>g</em><sub>1</sub><em>,g</em><sub>2</sub><em>,…,g<sub>k</sub></em>) = <sup>X</sup><em>cost</em>(<em>g<sub>i</sub></em>)

<em>i</em>=1

<em>cost</em>(<em>g<sub>i</sub></em>) is the sum of squared distances of all its constituent points to the center <em>c<sub>i</sub></em>, or

<em>cost</em>(<em>g<sub>i</sub></em>) = <sup>X </sup><em>dist</em><sup>2</sup>(<em>p,c<sub>i</sub></em>)

<em>p</em>∈<em>g<sub>i</sub></em>

<em>dist</em>() is the Euclidean distance. Now show that the cost of <em>k </em>clusters as evaluated at the end of each iteration (i.e., after Line 9 in the current algorithm) never increases. (You may assume <em>d </em>= 2)

(3) Prove that the cost of clusters obtained by <em>k</em>-means algorithm always converges to a local minima. You can make use of the previous conclusion even if you have not proved it.


