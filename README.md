# signal_path_analysis
Programs developed by Mateusz Fortunka during works on B.Sc. degree in Physics

I wrote presented programs to cover the last step of dynamical network analysis conducted in my B.Sc. thesis - processing the big amount of data generated from calculations of signal paths. The program released with tutorial to VMD NetworkView plugin ("subopt") gives a set of optimal and suboptimal paths with a small amount of additional information. It includes a number of paths, the most often encountered nodes and edges with their count. A program named "paths.py" takes all the output files from the "subopt" program in a folder (so from one trajectory) and gives a file with a summary for every path. Apart from the number of all found pathways and their average length with standard deviation, it also provides a number of mutated residues present in the paths. Also, it rewrites the most common aas from the "subopt" output file. Then, having summary files from all MD repeats, program "paths_summary.py" list specified pathways from every "paths.py" output file present in the folder. So its main idea is to put the data for every path together, which is useful for further analysis. Then three programs: "in_sum.py", "in_mirror.py" and "cross_sum.py" compare the data. The first two take "paths_summary.py" output file and calculate several values for every pathway. The output "in_sum.py" gives optimal path identity, average number of paths and length. It also provides an average count of mutated residues and standard deviation of all values. "In_mirror.py" comparison is similar, but it is not performed between data from MD repeats for one chosen pathway, but between "mirror" paths, which have the same starting nodes and targets, but their chains are changed. So for paths starting at the F185 in chain A and ending at E264 in chain B, the "mirror" path will be going from E264 in chain B to F185 in chain A. This example residues were taken from a wild variant of YARS2. The last program - "cross_sum.py" takes the same paths for two variants and compares them like in the "in_sum.py". It gives an output file with a difference of every value corresponding to the path between native and mutated YARS2.

