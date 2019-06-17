# PageRank-Implementation
  - PageRank (PR) is an algorithm used by Google Search to rank websites in their search engine results. PageRank was named after Larry       Page, one of the founders of Google. PageRank is a way of measuring the importance of website pages. According to Google:
  
    PageRank works by counting the number and quality of links to a page to determine a rough estimate of how important the website is.       The underlying assumption is that more important websites are likely to receive more links from other websites.
I have made a funciton which does pageRanking and here it is--> (along with explained arguments)

def pagerank(G, alpha=0.85, personalization=None, 
             max_iter=100, tol=1.0e-6, nstart=None, weight='weight', 
             dangling=None): 
             
    """Return the PageRank of the nodes in the graph. 
  
    PageRank computes a ranking of the nodes in the graph G based on 
    the structure of the incoming links. It was originally designed as 
    an algorithm to rank web pages. 
  
    Parameters 
    ---------- 
    G : graph 
      A NetworkX graph.  Undirected graphs will be converted to a directed 
      graph with two directed edges for each undirected edge. 
  
    alpha : float, optional 
      Damping parameter for PageRank, default=0.85. 
  
    personalization: dict, optional 
      The "personalization vector" consisting of a dictionary with a 
      key for every graph node and nonzero personalization value for each node. 
      By default, a uniform distribution is used. 
  
    max_iter : integer, optional 
      Maximum number of iterations in power method eigenvalue solver. 
  
    tol : float, optional 
      Error tolerance used to check convergence in power method solver. 
  
    nstart : dictionary, optional 
      Starting value of PageRank iteration for each node. 
  
    weight : key, optional 
      Edge data key to use as weight.  If None weights are set to 1. 
  
    dangling: dict, optional 
      The outedges to be assigned to any "dangling" nodes, i.e., nodes without 
      any outedges. The dict key is the node the outedge points to and the dict 
      value is the weight of that outedge. By default, dangling nodes are given 
      outedges according to the personalization vector (uniform if not 
      specified). This must be selected to result in an irreducible transition 
      matrix (see notes under google_matrix). It may be common to have the 
      dangling dict to be the same as the personalization dict. 
  
    Returns 
    ------- 
    pagerank : dictionary 
       Dictionary of nodes with PageRank as value 
  
    Notes 
    ----- 
    The eigenvector calculation is done by the power iteration method 
    and has no guarantee of convergence.  The iteration will stop 
    after max_iter iterations or an error tolerance of 
    number_of_nodes(G)*tol has been reached. 
  
    The PageRank algorithm was designed for directed graphs but this 
    algorithm does not check if the input graph is directed and will 
    execute on undirected graphs by converting each edge in the 
    directed graph to two edges. 
  
      
    """
