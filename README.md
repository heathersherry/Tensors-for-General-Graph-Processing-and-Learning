## Tensors-for-General-Graph-Processing-and-Learning

### Graph Algorithms in Linear Algebra Representation
Note: The idea of linear representation of graph algorithms has been under active community development since 2013.
1. Standards for Graph Algorithm Primitives [[Paper](http://www.netlib.org/utk/people/JackDongarra/PAPERS/GraphPrimitives-HPEC.pdf)]
> * The representation of graphs as sparse matrices allows many graph algorithms to be represented in terms of a modest set of linear algebra operations
> * The	state	of	the	art	in constructing	a	large	collection	of	graph	algorithms	in terms	of	linear	algebraic	operations	is	mature	enough	to	support	the emergence	of	a	standard set	of	primitive	building	blocks. This	paper	is	a	position	paper	defining	the	problem	and	announcing	our	intention	to	launch	an	open	effort	to	define	this	standard.
2. GraphBLAS Template Library (GBTL) [[Github](https://github.com/cmu-sei/gbtl)] [[Forum](https://graphblas.github.io)] [[Community](https://github.com/GraphBLAS/GraphBLAS-Pointers)]
> * the GraphBLAS API can be considered as a standard interface to represent graph algorithms in a linear algebraic way.
> * Example: Minimum Spanning Tree on GraphBLAS [[Link](https://github.com/cmu-sei/gbtl/blob/master/src/algorithms/mst.hpp)]
> * Summary 1: There are still graph algorithms that have any known algebraic representation: maximal clique enumeration problem, A* search, community detection methods, network flow, traveling salesman...
> * Summary 2: There are a group of algorithms that do not have satisfactory efficiecny in GraphBLAS: Algorithms that are inherently sequential such as depth-first search, and algorithms that use priority queues such as Dijkstra’s algorithm.”
- Graphs, Matrices, and the GraphBLAS: Seven Good Reasons [[Paper](https://arxiv.org/ftp/arxiv/papers/1504/1504.01039.pdf)] (Good overview)
- GraphBLAS: Graph Algorithms in the Language of Linear Algebra [[Slides 1](https://sites.cs.ucsb.edu/~gilbert/talks/Gilbert-27Jun2019.p)] [[Slides 2](https://sites.cs.ucsb.edu/~gilbert/cs240a/slides/old/cs240a-GALA.pdf)] (Good overview)
- Introduction to GraphBLAS [[Slides 1](http://mit.bme.hu/~szarnyas/grb/graphblas-introduction.pdf)] [[Slides 2](https://archive.fosdem.org/2020/schedule/event/graphblas/attachments/slides/4132/export/events/attachments/graphblas/slides/4132/graphblas_introduction.pdf)] [[Slides 3](https://archive.fosdem.org/2020/schedule/event/graphblas/attachments/slides/4053/export/events/attachments/graphblas/slides/4053/graphblas_fosdem_2020.pdf)] [[Talk](https://av.tib.eu/media/47516)] (Good overview)
- Implementing Push-Pull Efficiently in GraphBLAS (ICPP 2018) [[Paper](https://arxiv.org/pdf/1804.03327.pdf)]
- List of GraphBLAS-related books, papers, presentations, posters, and software [[Github](https://github.com/GraphBLAS/GraphBLAS-Pointers)]
- Library of GraphBLAS algorithms [[Github](https://github.com/GraphBLAS/LAGraph)]
- LAGraph: A Community Effort to Collect Graph Algorithms Built on Top of the GraphBLAS (What’s next for the GraphBLAS?)

__Related Reading__
1. Graph Processing on GPUs: A Survey [[Paper](https://www.dcs.warwick.ac.uk/~liganghe/papers/ACM-Computing-Surveys-2017.pdf)]
> *  This article surveys the key issues of graph processing on GPUs, including data layout, memory access pattern, workload mapping, and specific GPU programming.
2. Graph Algorithms in the Language of Linear Algebra (The GALLA Book 2011) [[Slides](https://sites.cs.ucsb.edu/~gilbert/cs240a/slides/old/cs240a-GALA.pdf)]

### Graph Data Processing and Query on Tensors
1. Tensors: An abstraction for general data processing (VLDB 2021) (The Hummingbird project) [[Paper](http://vldb.org/pvldb/vol14/p1797-koutsoukos.pdf)] [[Github](https://github.com/microsoft/hummingbird)]
> * Motivation: The implementations of GraphBLAS turn out to be suboptimal when executed over TCRs, because they rely on sparse representations of the graph, while TCRs are not efficient for sparse computations. Hence, novel implementations are required...
> * This work explores to what extent Tensor Computation Runtimes (TCRs) can support *non-ML* data processing applications, e.g, PageRANK.
> * Section 4 also mentions that tensors are applicable to complex query such as selection, join and aggration, but there is no detail or exmaple provided in the paper (except for cardinality calculation).

### Machine Learning on Tensors 

2. Exploiting tensor networks for efficient machine learning (PhD thesis) [[Link](https://hub.hku.hk/handle/10722/308618)]
> * This thesis explores the tensorization and compression of machine learning models (SVMs and RBMs).
3. A Tensor Compiler for Unified Machine Learning Prediction Serving (OSDI 2020) (The Hummingbird project) [[Paper](https://web.eecs.umich.edu/~mosharaf/Readings/Hummingbird.pdf)]
> * It compiles featurization operators and traditional ML models (e.g., decision trees) into a small set of tensor operations.
4. Compiling Classical ML Pipelines into Tensor Computations for One-size-fits-all Prediction Serving (System for ML Workshop, NeurIPS 2019) (The Hummingbird project) [[Paper](http://learningsys.org/neurips19/assets/papers/27_CameraReadySubmission_Hummingbird%20(5).pdf)]
> * It compile classical ML pipelines end-to-end into tensor computations. It thereby seamlessly leverages the features provided by DNN inference systems, e.g., ease of deployment, operator optimizations and GPU support.

### Graph Representation and Learning on Tensors
1. Tensor Graph Convolutional Networks for Prediction on Dynamic Graphs (submitted to ICLR 2019, but rejected) [[Paper](https://openreview.net/forum?id=rylVTTVtvH)]
> * This work learns embeddings of dynamic graphs based on a tensor algebra framework
> * Tensor M-product technique
> * Comments: (1) the proposed tensor method lacks novelty, (2) the theoretical analysis is artificial, and (3) the empirical study does not cover enough benchmarks. 
2. Dynamic Graph Convolutional Networks Using the Tensor M-Product (SDM 2019) [[Paper](https://arxiv.org/pdf/1910.07643)] [[Github](https://github.com/IBM/TM-GCN)]
> * This work combines adjancency tensor and feature tensor.

### Related Readings
1. Tensor Algebra and Tensor Analysis for Engineers (2015) [[Springer](https://link.springer.com/book/10.1007/978-3-319-16342-0)]
2. Deep-Learning-with-PyTorch (book)
> * Chapter 2: It starts with a tensor
> * Chapter 3: Representing the real-world data with tensors
> * Tutorial: How to store a Tensor? [[Link](https://blog.csdn.net/ZM_Yang/article/details/105587634)]
6. Tensor Processing Primitives: A Programming Abstraction for Efficiency and Portability in Deep Learning & HPC Workloads (Arxiv 2021) [[Paper](https://arxiv.org/pdf/2104.05755.pdf)]
7. FreeTensor: A Free-form DSL with Holistic Optimization for Irregular Tensor Programs (accpeted in PLDI 2022, no source yet)
8. Graphs, Matrices, and the GraphBLAS: Seven Good Reasons (ICCS 2015)
9. Tensor Completion for Weakly-Dependent Data on Graph for Metro Passenger Flow Prediction (AAAI 2020) [[Paper](https://ojs.aaai.org//index.php/AAAI/article/view/5915)]
10. Tensor Graph Convolutional Networks for Multi-relational and Robust Learning (arxiv 2020) [[Paper](https://arxiv.org/abs/2003.07729)]
