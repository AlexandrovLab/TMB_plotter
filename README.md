# TMB_plotting_function

```
plotTMB(inputDF, scale, Yrange = "adapt", cutoff = 1, output = "TMB_plot.pdf")
```
## Usage

1. **inputDF**:  *A panda dataframe containing two columns and however many rows of samples.* 
```
Column 1 is the category the sample belongs to. 
Column 2 is the number of mutations in that sample.
```            
**Example:**

| Column1 | Column2 |
|-------------|-------|
| Bladder-TCC | 25212 |
| Bladder-TCC | 31114 |
| Bladder-TCC | 36432 |
    

2. **scale**:  *The number of base pairs sequenced in each sample.*
```
The options are: 
"exome", which assumes sequencing size of 55 Mb
"genome", which assumes sequencing size of 2800 Mb
An integer indicating the scale of the sequencing
```
3. **Yrange**:  *The range of Yaxis.*
```
The options are:
"adapt", which will make the plot automatically adapt to the given datase
"cancer", which will set the range to 0.001 to 1000
A list of two numbers of powers of 10 indicating the Y-axis range. Example: [0.1,100]
```
4. **cutoff**:  *The mimum number of mutations required in a sample to be included in a plot*
```
defaulted at 1
```
5. **output**:  *outputfile name*
```
defaulted is "TMB_plot.pdf"
```
## Examples
Example 1:  Y axis adapts to input data
```
inputDF = pd.read_table('exmapleInput2_pcawg_less.txt')
plotTMB(inputDF,"genome", "adapt")
```
![Alt text](plots/E1_adapt.png?raw=true "Example 1:Y axis adapts to input data")


Example 2:  Y axis set for standard cancer TMB range
```
inputDF = pd.read_table('exmapleInput2_pcawg_less.txt')
plotTMB(inputDF,"genome", "cancer")
```
![Alt text](plots/E1_cancer.png?raw=true "Example 2:Y axis set for standard cancer TMB")


Exmaple 3:  Using custome input value for sequencing scale and Y axis range
```
inputDF = pd.read_table('exmapleInput2_pcawg_less.txt')
plotTMB(inputDF,2800, [0.1,10])
```
![Alt text](plots/E1_list.png?raw=true "Exmaple 3: custome input value for sequencing scale and Y axis range")


Exmaple 4:  Using cutoff to remove lower end outliers
```
inputDF = pd.read_table('exmapleInput3_signature.txt')
plotTMB(inputDF,"genome",cutoff =2)
```
![Alt text](plots/E3_cutoff.png?raw=true "Exmaple 4: Cutoff")


Exmaple 5:  The full PCAWG dataset
```
inputDF = pd.read_table('exmapleInput1_pcawg.txt')
plotTMB(inputDF,"genome","adapt")
```
![Alt text](plots/E2_adapt.png?raw=true "Exmaple 5: full PCAWG dataset")
