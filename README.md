Download Link: https://assignmentchef.com/product/solved-cs3431-homework-6
<br>
<strong>Problem 1</strong>

For the relational schema given below and the corresponding functional dependencies (FDs)

R(A, B, C, D, E ) S = { AB à E, B à C, B à D, CE à A },

answer the following questions:




<ol>

 <li> find all candidate keys of the relation R through an exhaustive set of attribute closures. Note when an attribute set closure is trivial.</li>

 <li> Assume that S is a minimal basis for R. List the dependencies that violate <strong>3NF</strong>, if any.</li>

</ol>




<ol>

 <li>(5 points) If R is NOT in <strong>3NF</strong>, decompose it into multiple relations that are in <strong>3NF</strong>.</li>

 <li>(5 points) List the dependencies, in the order given in S, that violate <strong>BCNF</strong>.</li>

</ol>

B -&gt; C (not trivial, B not super key)

B -&gt; D (not trivial, B not super key)

CE -&gt; A (not trivial, CE not super key)




<ol>

 <li>(10 points) If R is not in <strong>BCNF</strong>, provide decomposition into multiple relations where each one is in BCNF. For each decomposition step, use the first FD violation following the FD order given in S. For example, if AB à E and B à C are in BCNF but the other two FDs are in violation, then you would use B à D for the decomposition. Make sure to specify which FD is used to make the decomposition.</li>

</ol>







<strong>Problem 2 (45 Points)</strong>

For the relational schema given below and its corresponding functional dependencies (FDs)

R(A, B, C, D, E )        S = { B à A, B à E, CE à D, D à B }

answer the following questions:




<ol>

 <li> find all candidate keys of the relation through an exhaustive set of attribute closures. Note when an attribute set closure is trivial.</li>

 <li>Decompose the relations to satisfy BCNF. Specify which FD is used to make the decomposition. If there is multi-step decomposition, then indicate each step along with which FD is used for the decomposition.</li>

 <li> If the FDs are not in 3NF, calculate a minimal basis for the FDs and decompose the relations to satisfy 3NF.</li>

 <li>Indicate whether each of the following decompositions is Lossy or Lossless and state why?

  <ol>

   <li>Artist and Artwork are in one relation. Gallery, Address, and Artwork are in the other relation.</li>

  </ol></li>

</ol>

This is a <strong>lossless</strong> decomposition -&gt; a natural join of the 2 relations would produce the original relation.

Another way to look at this is the following:

The common attributes of the two relations is just the Artwork.

Since the artwork is a key for both relations (i.e. Artwork -&gt; Artist and Artwork -&gt; Gallery,Address), the decomposition is lossless.




<ol>

 <li>Gallery, Address, and Artwork are in one relation. Artist and Gallery are in one relation.</li>

</ol>

This is a <strong>lossy</strong> decomposition -&gt; a natural join would create extra records for the Miami Beach Gallery

Another way to look at this:

The common attributes of the two relations is just the Gallery.

Since Gallery is not a key in either of them (i.e. Gallery –x&gt; Artist and Gallery –x&gt; Arist,Address), the decomposition is lossy.







<ol start="2">

 <li>(10 Points) Identify and list the set of functional dependencies from the data in the table above. Then, specify which of the following decompositions preserve those dependencies, and state why.</li>

</ol>




<strong>Note</strong>: it may help to draw the relations to visualize what may have changed through decomposition.

<ol>

 <li>Gallery, Address, and Artist are in one relation. Artwork and Artist are in the other relation.</li>

</ol>




<table>

 <tbody>

  <tr>

   <td width="226"> </td>

   <td width="226"> </td>

   <td width="226"> </td>

  </tr>

  <tr>

   <td width="226"> </td>

   <td width="226"> </td>

   <td width="226"> </td>

  </tr>

  <tr>

   <td width="226"> </td>

   <td width="226"> </td>

   <td width="226"> </td>

  </tr>

  <tr>

   <td width="226"> </td>

   <td width="226"> </td>

   <td width="226"> </td>

  </tr>

  <tr>

   <td width="226"> </td>

   <td width="226"> </td>

   <td width="226"> </td>

  </tr>

 </tbody>

</table>







<table>

 <tbody>

  <tr>

   <td width="338"> </td>

   <td width="338"> </td>

  </tr>

  <tr>

   <td width="338"> </td>

   <td width="338"> </td>

  </tr>

  <tr>

   <td width="338"> </td>

   <td width="338"> </td>

  </tr>

  <tr>

   <td width="338"> </td>

   <td width="338"> </td>

  </tr>

  <tr>

   <td width="338"> </td>

   <td width="338"> </td>

  </tr>

 </tbody>

</table>




For the two tables individually we can see the following:




A natural Join of the Two Tables Would Looks as Follows




<table>

 <tbody>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

 </tbody>

</table>




We can see from the natural join the following:




Preserves:                     Gallery -&gt; Address

Artwork -&gt; Artist

Artist -&gt; Address

Artwork -&gt; Address




Doesn’t preserve:          Artwork -&gt; Gallery

Artist,Gallery -&gt; Artwork







Since we can only join the tables on the Artist, we have no way of assigning a unique Gallery or Address to an Artwork. We’ve also lost the ability to imply the Artwork using the Artist and the Gallery.




<ol>

 <li>Gallery, Artist are in one relation. Artwork, Artist, and Address are in the other relation.</li>

</ol>




<table>

 <tbody>

  <tr>

   <td width="307"> </td>

   <td width="310"> </td>

  </tr>

  <tr>

   <td width="307"> </td>

   <td width="310"> </td>

  </tr>

  <tr>

   <td width="307"> </td>

   <td width="310"> </td>

  </tr>

  <tr>

   <td width="307"> </td>

   <td width="310"> </td>

  </tr>

  <tr>

   <td width="307"> </td>

   <td width="310"> </td>

  </tr>

 </tbody>

</table>







<table>

 <tbody>

  <tr>

   <td width="234"> </td>

   <td width="230"> </td>

   <td width="213"> </td>

  </tr>

  <tr>

   <td width="234"> </td>

   <td width="230"> </td>

   <td width="213"> </td>

  </tr>

  <tr>

   <td width="234"> </td>

   <td width="230"> </td>

   <td width="213"> </td>

  </tr>

  <tr>

   <td width="234"> </td>

   <td width="230"> </td>

   <td width="213"> </td>

  </tr>

  <tr>

   <td width="234"> </td>

   <td width="230"> </td>

   <td width="213"> </td>

  </tr>

 </tbody>

</table>




From the two tables individually we can see the following:










A natural join of the two tables would look as follows:

<table>

 <tbody>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

  <tr>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

   <td width="169"> </td>

  </tr>

 </tbody>

</table>




From the natural join we can see the following:




Since we can only join the tables on the Artist, we have no way of assigning a unique Gallery or Address to an Artwork. We’ve also lost the ability to imply the Artwork using the Artist and the Gallery.





