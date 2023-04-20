# page-rank

PageRank algorithm can be used to evaluate relative importance of nodes in a connected environment.
It is based on the concept of in-links and out-links of a node and is used to rank nodes in a graph
in order of their importance.

Data:

1. Go to https://transtats.bts.gov/

2. On the left menu, click under “Aviation” under the “By Mode” block.

3. On the next page, click Air Carrier Statistics (Form 41 Traffic)- U.S. Carriers

4. On the next page, click download link under T-100 Domestic Segment (U.S. Carriers)

5. On the next page, set Filter Year = Most Recent Year, Filter Period = Any month on which
data is available (e.g. July), and select following fields:

  • Origin (Origin Airport Code)
  
  • OriginCityName (optional)

  • Dst (Destination Airport Code)
  
  • DstCityName (optional)
  
6. Download and unzip to get a csv file.



1. The program has 3 parameters:

  1. Location of the csv file containing the fields mentioned above. The file should be hosted on
  AWS S3 or any other public location.
  
  2. Maximum number of iterations to run.
  
  3. Location of output file. Output stored on AWS S3.
  
  These arguments can be read from the user on the command line or through an input file.
  
2. Computed the page rank of each node (airport) based on number of inlinks and outlinks.
There may be multiple connections between two airports, and they are considered independent
of each other to compute the number of inlinks and outlinks. For example, if node A
is connected to node B with an out-count of 10 and node C with an out-count of 10, then the
total number of outlinks for node A would be 20.

3. Initialized all the PageRank values to be 10.0
