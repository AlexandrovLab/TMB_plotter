# TMB_plotting_function

**Inputs**

1. inputDF: A panda dataframe containing two columns and however many rows of samples. 
            Column 1 is the category the sample belongs to. 
            Column 2 is the number of mutations in that sample.
            
Example:
    | speed | Re_tip | Re_root | Re_ave | Re_D
---|--------|-------|--------|--------|--------
0 | 4.0e-01 | 5.0e+04 | 8.3e+04 | 6.6e+04 | 4.3e+05
1 | 6.0e-01 | 7.4e+04 |  1.2e+05 | 9.9e+04 | 6.4e+05
2 | 8.0e-01 | 9.9e+04 | 1.7e+05 | 1.3e+05 | 8.6e+05
3 | 1.0e+00 | 1.2e+05 |  2.1e+05 | 1.7e+05 | 1.1e+06
4 | 1.2e+00 | 1.5e+05 |  2.5e+05 | 2.0e+05 | 1.3e+0

2. scale: "exome" or "genome" or an integer indicating the scale of the sequencing
3. Yrange: The range of Yaxis. The options are either "adapt", which will make the plot automatically adapt to the given dataset, or "cancer", which will set the range to 0.001 to 1000, or a list of two numbers of powers of 10 indicating the Y-axis range.
