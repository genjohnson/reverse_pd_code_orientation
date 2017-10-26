# Puprose
Switch between clockwise and counterclockwise traversal of edges for generating planar diagram (PD) codes.

This is useful when using PD codes between Knotinfo ([http://www.indiana.edu/~knotinfo/](http://www.indiana.edu/~knotinfo/)) and Sage.

# How to run the script
1. Create a CSV file containing the planar diagram codes to reverse and strings ("name") to identify each PD code formatted as follows:
```
name,pd_notation
3_1,"[[1,5,2,4],[3,1,4,6],[5,3,6,2]]"
4_1,"[[4,2,5,1],[8,6,1,5],[6,3,7,4],[2,7,3,8]]"
5_1,"[[2,8,3,7],[4,10,5,9],[6,2,7,1],[8,4,9,3],[10,6,1,5]]"
5_2,"[[1,5,2,4],[3,9,4,8],[5,1,6,10],[7,3,8,2],[9,7,10,6]]"
```
2. Run `./generate_reverse_pd_codes.py -i <path to input file>`
3. The output file is located at `pd_codes/sage.csv` and is formatted like the following:
```
name, sage_pd_code
sage_3_1,"[[1,4,2,5],[3,6,4,1],[5,2,6,3]]"
sage_4_1,"[[4,1,5,2],[8,5,1,6],[6,4,7,3],[2,8,3,7]]"
sage_5_1,"[[2,7,3,8],[4,9,5,10],[6,1,7,2],[8,3,9,4],[10,5,1,6]]"
sage_5_2,"[[1,4,2,5],[3,8,4,9],[5,10,6,1],[7,2,8,3],[9,6,10,7]]"
```

Note that while the name of output file and the name of each PD code it contains is currently hard-coded with "sage" (the original use of the scipt was to generate PD codes to put into Sage to generate diagrams with PD codes from KnotInfo), the script handles the reverse case of taking in PD codes which were used with Sage and outputting PD codes with the orientation used on KnotInfo.
