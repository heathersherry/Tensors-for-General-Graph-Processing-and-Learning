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
- GraphBLAS materials [[Link](http://mit.bme.hu/~szarnyas/grb/)]
- GraphBLAS in Python [[Github](https://github.com/Graphegon/pygraphblas)]
- GraphBLAST [[Github](https://github.com/gunrock/graphblast)]
3. Navigating the Maze of Graph Analytics Frameworks using Massive Graph Datasets (SIGMOD 2014) [[Paper](https://mobisocial.stanford.edu/papers/sigmod14n.pdf)]

__Related Reading__
1. Graph Processing on GPUs: A Survey [[Paper](https://www.dcs.warwick.ac.uk/~liganghe/papers/ACM-Computing-Surveys-2017.pdf)]
> *  This article surveys the key issues of graph processing on GPUs, including data layout, memory access pattern, workload mapping, and specific GPU programming.
2. Graph Algorithms in the Language of Linear Algebra (The GALLA Book 2011) [[Slides](https://sites.cs.ucsb.edu/~gilbert/cs240a/slides/old/cs240a-GALA.pdf)]
3. Industrial implementaion of GraphBLAS
> - Huawei GraphBLAS [[Gitee](https://gitee.com/CSL-ALP/graphblas)]
> - IBM GraphBLAS [[Github](https://github.com/IBM/ibmgraphblas)]

__BFS__
1. A good example of BFS in vector-matrix multiplication [[Slides](https://archive.fosdem.org/2020/schedule/event/graphblas/attachments/slides/4132/export/events/attachments/graphblas/slides/4132/graphblas_introduction.pdf)]
2. Direction-Optimizing Breadth-First Search (SC 2012, adopted to GraphBLAS in 2018)
> * Switches between push (𝐯𝐀) and pull (𝐀 ⊤𝐯) during execution:
>> Use the push direction when the frontier is small; Use the pull direction when the frontier becomes large
3. High-performance linear algebra-based graph framework on the GPU (PhD thesis, UC Davis 2019)
> * Chapter 5 is a more detailed and corrected version of the 4th paper
4. Implementing Push-Pull Efficiently in GraphBLAS (ICPP 2018)
6. [Just For Reference] GraphBLAS: Concepts, algorithms, and applications (Scheduling Workshop 2019)
7. Optimal algebraic Breadth-First Search for sparse graphs (preprint, 2019)
8. A GraphBLAS solution to the SIGMOD 2014 Programming Contest using multi-source BFS (HPEC 2020)

__DFS__
1. Linear Algebraic Depth-First Search (ARRAY workshop @ PLDI 2019)

__Shortest Path__
1. [Just For Reference] Shortest-path kernels on graphs [[Paper](https://www.dbs.ifi.lmu.de/~borgward/papers/BorKri05.pdf)]
2. Delta-Stepping SSSP: From Vertices and Edges to GraphBLAS Implementations (GrAPL @ IPDPS 2019)
> * In its Preliminaries section, this paper contains the translation of a few vertex-centric and edge-centric design patterns to linear algebra.
3. Path Problems in Networks (Morgan & Claypool Publishers, 2010) 
> * This book is about the algebraic path problem – a semiring-based generalization of shortest path problem. The mathematical foundations of semiring-based graph analysis are described. Basic ideas to create new semirings to solve new problems are described.
> * The section 3.1 "Alternative viewpoints: paths and matrices" (p17-19) provides a matrix-based framework for the algebraic path problem which is highly relevant to GraphBLAS.
> * The table on pages 58-59 contains 29 different semirings and respective applied problems.

__Connected Components__
1. Parallel algorithms for finding connected components using linear algebra (Journal of Parallel and Distributed Computing 2020) 
2. FastSV: A Distributed-Memory Connected Component Algorithm with Fast Convergence (PP 2020)
3. LACC: A Linear-Algebraic Algorithm for Finding Connected Components in Distributed Memory (IPDPS 2019) 

__PageRank__
1. The GraphBLAS in Julia and Python:the PageRank and Triangle Centralities (HPEC 2021)
2. GraphBLAS: Handling performance concerns in large graph analytics – invited paper (CF 2018) [[Paper](https://www.ibm.com/university/power/images/CF2018.pdf)]

### Graph Data Processing (and Query) on Tensors
1. Tensors: An abstraction for general data processing (VLDB 2021) (The Hummingbird project) [[Paper](http://vldb.org/pvldb/vol14/p1797-koutsoukos.pdf)] [[Github](https://github.com/microsoft/hummingbird)]
> * Motivation: The implementations of GraphBLAS turn out to be suboptimal when executed over TCRs, because they rely on sparse representations of the graph, while TCRs are not efficient for sparse computations. Hence, novel implementations are required...
> * This work explores to what extent Tensor Computation Runtimes (TCRs) can support *non-ML* data processing applications, e.g, PageRANK.
> * Section 4 also mentions that tensors are applicable to complex query such as selection, join and aggration, but there is no detail or exmaple provided in the paper (except for cardinality calculation).
2. Graph Traversal with Tensor Functionals: A Meta-Algorithm for Scalable Learning (ICLR 2021) [[Paper](https://openreview.net/forum?id=6DOZ8XNNfGN)]


### Machine Learning on Tensors 
1. Exploiting tensor networks for efficient machine learning (PhD thesis) [[Link](https://hub.hku.hk/handle/10722/308618)]
> * This thesis explores the tensorization and compression of machine learning models (SVMs and RBMs).
2. A Tensor Compiler for Unified Machine Learning Prediction Serving (OSDI 2020) (The Hummingbird project) [[Paper](https://web.eecs.umich.edu/~mosharaf/Readings/Hummingbird.pdf)]
> * It compiles featurization operators and traditional ML models (e.g., decision trees) into a small set of tensor operations.
3. Compiling Classical ML Pipelines into Tensor Computations for One-size-fits-all Prediction Serving (System for ML Workshop, NeurIPS 2019) (The Hummingbird project) [[Paper](http://learningsys.org/neurips19/assets/papers/27_CameraReadySubmission_Hummingbird%20(5).pdf)]
> * It compile classical ML pipelines end-to-end into tensor computations. It thereby seamlessly leverages the features provided by DNN inference systems, e.g., ease of deployment, operator optimizations and GPU support.
4. WindTunnel: Towards Differentiable ML Pipelines Beyond a Single Model (VLDB 2021) [[Paper](https://dl.acm.org/doi/pdf/10.14778/3485450.3485452)]
> * It extends HummingBird by enabling conversion of pipelines into differential modules.

### Graph Representation and Learning on Tensors
__Note:__ So far, the papers in this category still focus on model design, instead of tensor computation.
1. Tensor Graph Convolutional Networks for Prediction on Dynamic Graphs (submitted to ICLR 2019, but rejected) [[Paper](https://openreview.net/forum?id=rylVTTVtvH)]
> * This work learns embeddings of dynamic graphs based on a tensor algebra framework.
> * Tensor M-product technique.
> * Comments: (1) the proposed tensor method lacks novelty, (2) the theoretical analysis is artificial, and (3) the empirical study does not cover enough benchmarks. 
2. Dynamic Graph Convolutional Networks Using the Tensor M-Product (SDM 2019) [[Paper](https://arxiv.org/pdf/1910.07643)] [[Github](https://github.com/IBM/TM-GCN)]
> * This work combines adjancency tensor and feature tensor
3. Tensor Graph Convolutional Networks for Multi-relational and Robust Learning (arxiv 2020) [[Paper](https://arxiv.org/abs/2003.07729)]

### Query and Relational Algebra on Tensors
1. Tensor Relational Algebra for Distributed Machine Learning System Design (VLDB 2021) [[Paper](http://www.vldb.org/pvldb/vol14/p1338-yuan.pdf)] 
> * They use relational algebra expressions to improve tensors.
3. There are a set of studies about relation algebra in LA in GraphBLAS [[A good summary](http://mit.bme.hu/~szarnyas/grb/graphblas-outlook-to-other-fields.pdf)]
4. Serving Deep Learning Models with Deduplication from Relational Databases (arxiv 2021) [[Paper](https://arxiv.org/pdf/2201.10442.pdf)]
5. Query Processing on Tensor Computation Runtimes [[Paper](https://arxiv.org/pdf/2203.01877.pdf)] [[Blog](https://medium.com/syncedreview/meet-tqp-the-first-query-processor-to-run-on-tensor-computation-runtimes-delivers-up-to-20x-7d1f09d3b9f8)] [[News](https://www.marktechpost.com/2022/03/13/researchers-from-the-university-of-washington-and-uc-san-diego-introduce-tensor-query-processor-tqp-with-tensor-computation-runtimes-for-query-processing-20x-speedup/)]
> * Tensor Query Processor (TQP): a SQL query processor leveraging the tensor interface of TCRs

### Tensor Compilers
1. A High-Performance Sparse Tensor Algebra Compiler in Multi-Level IR [[Paper](https://arxiv.org/pdf/2102.05187.pdf)]
2. THE CORA TENSOR COMPILER: COMPILATION FOR RAGGED TENSORS WITH MINIMAL PADDING [[Paper](https://www.pdl.cmu.edu/ftp/BigLearning/fegade-2110.10221.pdf)]
> * They propose a compiler-based solution enabling easy and more portable generation of performant code for ragged operators. While sparse (Tian et al.,
2021; Kjolstad et al., 2017) and dense (Chen et al., 2018a; Vasilache et al., 2018; Ragan-Kelley et al., 2013; Baghdadi et al., 2019) tensor compilers have been well-studied, it is not straightforward to apply these techniques to ragged tensors.

### Related Readings and Background Materials
1. Tensor Algebra and Tensor Analysis for Engineers (2015) [[Springer](https://link.springer.com/book/10.1007/978-3-319-16342-0)]
2. Deep-Learning-with-PyTorch (book)
> * Chapter 2: It starts with a tensor
> * Chapter 3: Representing the real-world data with tensors
> * Tutorial: How to store a Tensor? [[Link](https://blog.csdn.net/ZM_Yang/article/details/105587634)]
6. Tensor Processing Primitives: A Programming Abstraction for Efficiency and Portability in Deep Learning & HPC Workloads (Arxiv 2021) [[Paper](https://arxiv.org/pdf/2104.05755.pdf)]
> * Tensor Processing Primitives (TPP): a programming abstraction striving for efficient and portable implementation of Tensor operations, with a special focus on DL workloads. 
> * TPPs define a set of relatively low-level primitive operators on 2D Tensors, which in turn can be used as basic building blocks to construct more complex operators on high-dimensional tensors. T
8. FreeTensor: A Free-form DSL with Holistic Optimization for Irregular Tensor Programs (accpeted in PLDI 2022, no source yet)
9. Tensor Completion for Weakly-Dependent Data on Graph for Metro Passenger Flow Prediction (AAAI 2020) [[Paper](https://ojs.aaai.org//index.php/AAAI/article/view/5915)]
10. A brief survey of tensors [[Slides 1](https://www.slideshare.net/BertonEarnshaw/a-brief-survey-of-tensors)] [[Slides 2](https://documents.pub/document/a-brief-survey-of-tensors.html?page=1)] 
> * Introduction to the Tensor Train Decomposition and Its Applications in Machine Learning [[Slides](https://bayesgroup.github.io/team/arodomanov/tt_hse16_slides.pdf)]
> * Most Tensor Problems are NP-Hard (2013) [[Paper](https://arxiv.org/pdf/0911.1393.pdf)]
> * Hardware-Enabled Efficient Data Processing with Tensor-Train Decomposition [[Paper](https://web.ece.ucsb.edu/~zhengzhang/journals/2021_TCAD_Qu_TTEngine.pdf)]
> * The Tensor-Train Format and Its Applications (PhD thesis) [[Thesis](https://refubium.fu-berlin.de/bitstream/handle/fub188/3366/dissertation_pg_final.pdf?sequence=1)]
11. Generating Efficient Tensor Contractions for GPUs [[Paper](https://www.mcs.anl.gov/papers/P5361-0615.pdf)]
12. TENSOR NETWORK SKELETONIZATION (2017) [[Paper](https://web.stanford.edu/~lexing/tns.pdf)]
13. The Gunrock series [[Link](https://gunrock.github.io/docs/#/gunrock/publications_and_presentations)]
> * Gunrock: A High-Performance Graph Processing Library on the GPU [[Paper](https://arxiv.org/pdf/1501.05387.pdf)], which evaluate Gunrock on five graph
primitives (BFS, BC, SSSP, CC, and PageRank).
14. [About CSR] Graph Storage: How good is CSR really? [[Paper](https://db.in.tum.de/teaching/ws1718/seminarHauptspeicherdbs/paper/valiyev.pdf)] 
15. An Experimental Comparison of Pregel-like Graph Processing Systems [[Paper](https://www.vldb.org/pvldb/vol7/p1047-han.pdf)]
16. A lightweight infrastructure for graph analytics [[Paper](https://dl.acm.org/doi/10.1145/2517349.2522739)]
17. [GraphBLAST] Design Principles for Sparse Matrix Multiplication on the GPU [[Paper](https://ehttps://www.pdl.cmu.edu/ftp/BigLearning/fegade-2110.10221.pdfscholarship.org/uc/item/5h35w3b7)]
18. THE CORA TENSOR COMPILER: COMPILATION FOR RAGGED TENSORS WITH MINIMAL PADDING [[Paper](https://www.pdl.cmu.edu/ftp/BigLearning/fegade-2110.10221.pdf)]
19. A High-Performance Sparse Tensor Algebra Compiler in Multi-Level IR (arxiv) [[Paper](https://arxiv.org/pdf/2102.05187.pdf)]
20. About torch.Tensor [[Link](https://zhuanlan.zhihu.com/p/51323438)]
