# FD_SAT_Plan

Factored Deep SAT Planner (FD-SAT-Plan) [1] is a two-stage planner based on the learning and planning framework [2] that (i) learns the state transition function of a factored [3] planning problem using Binarized Neural Networks [4] from data, and (ii) compiles the sequence of learned transition functions into CNF and solve it using off-the-shelf SAT solver [5].

## Improvements

I always look for ways to improve the runtime performance and memory efficiency of FD-SAT-Plan. Since the publication [1], the performance of FD-SAT-Plan has significantly improved due to smarter encodings of the binarized activation functions. Namely, cardinality networks [6] are currently used to replace the sequential cardinality [7] constraints used in [1].  

## Dependencies

Data collection (input to training BNN [4]): Data is collected using the RDDL-based domain simulator [8]. 

Training BNN: The publicly available code [9] is used to train BNNs. The final training parameters were recorded into bnn.txt and normalization.txt files.

Compilation to CNF: 

Solver: Any off-the-shelf SAT solver works. In our work [1], we used Glucose SAT solver [5].

## References
[1] Buser Say, Scott Sanner. Planning in Factored State and Action Spaces with Learned Binarized Neural Network Transition Models. In 27th IJCAI-ECAI, 2018.

[2] Buser Say, Ga Wu, Yu Qing Zhou, and Scott Sanner. Nonlinear hybrid planning with deep net learned transition models and mixed-integer linear programming. In 26th IJCAI, pages 750–756, 2017.

[3] Craig Boutilier, Thomas Dean, and Steve Hanks. Decision-theoretic planning: Structural assumptions and computational leverage. JAIR, 11(1):1–94, 1999.

[4] Itay Hubara, Matthieu Courbariaux, Daniel Soudry, Ran El-Yaniv, and Yoshua Bengio. Binarized neural networks. In 29th NIPS, pages 4107–4115. Curran Associates, Inc., 2016.

[5] Gilles Audemard and Laurent Simon. Lazy Clause Exchange Policy for Parallel SAT Solvers, pages 197–205. Springer Int. Publishing, 2014.

[6] Roberto Asin, Robert Nieuwenhuis, Albert Oliveras, Enric Rodriguez-Carbonell, Cardinality Networks and their Applications. International Conference on Theory and Applications of Satisfiability Testing, pages 167-180, 2009.

[7] Carsten Sinz. Towards an Optimal CNF Encoding of Boolean Cardinality Constraints, pages 827–831. Springer Berlin Heidelberg, Berlin, Heidelberg, 2005

[8] Relational dynamic influence diagram language (rddl): Language description. 2010.

[9] https://github.com/MatthieuCourbariaux/BinaryConnect

[10]
