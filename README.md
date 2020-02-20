# density_plot
visualize the point density of many data points. calculate the point density from an input file and generate a density file containing the point density for each grid cell which can be directly plotted by gnuplot.

the script runs from command line like:
get_point_density [input.dat] [output.dat] [x_range] [y_range] [col_1] [col_2] [grid size x (int)] [grid size y (int)] [x shift] [y shift]

where input.dat is the input file with data points in columns, output.dat the output file, x_range is the range of x and is bigger than your biggest x (in the input file), y_range is the range of y and is bigger than your biggest y (in the input file)
col 1 and col 2 are the numbers of the columns where your data is stored in the input file e.g. 1 2 for 1rst and 2nd column. grid size x y is the number of cells your space is divided into to calculate the density.
x shift and y shift can shift your calculation if your x or y values do not begin at 0.

to plot the output file in gnuplot use the following gnuplot code (where you ideally set the dgrid3d numbers to your grid size x and y) :
set dgrid3d 50,50
set view map
set pm3d
splot 'output.dat'
