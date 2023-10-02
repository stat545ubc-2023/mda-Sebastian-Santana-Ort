Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## Warning: package 'tidyverse' was built under R version 4.3.1

    ## Warning: package 'ggplot2' was built under R version 4.3.1

    ## Warning: package 'tibble' was built under R version 4.3.1

    ## Warning: package 'tidyr' was built under R version 4.3.1

    ## Warning: package 'readr' was built under R version 4.3.1

    ## Warning: package 'purrr' was built under R version 4.3.1

    ## Warning: package 'dplyr' was built under R version 4.2.3

    ## Warning: package 'stringr' was built under R version 4.3.1

    ## Warning: package 'forcats' was built under R version 4.3.1

    ## Warning: package 'lubridate' was built under R version 4.3.1

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2023>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

- Each milestone has explicit tasks. Tasks that are more challenging
  will often be allocated more points.

- Each milestone will be also graded for reproducibility, cleanliness,
  and coherence of the overall Github submission.

- While the two milestones will be submitted as independent
  deliverables, the analysis itself is a continuum - think of it as two
  chapters to a story. Each chapter, or in this case, portion of your
  analysis, should be easily followed through by someone unfamiliar with
  the content.
  [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/)
  is a good resource for what constitutes “good code”. Learning good
  coding practices early in your career will save you hassle later on!

- The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

- Become familiar with your dataset of choosing
- Select 4 questions that you would like to answer with your data
- Generate a reproducible and clear report using R Markdown
- Become familiar with manipulating and summarizing your data in tibbles
  using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

- *apt_buildings*: Acquired courtesy of The City of Toronto’s Open Data
  Portal. It currently has 3455 rows and 37 columns.

- *building_permits*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 20680 rows and 14 columns.

- *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository.
  It currently has 569 rows and 32 columns.

- *flow_sample*: Acquired courtesy of The Government of Canada’s
  Historical Hydrometric Database. It currently has 218 rows and 7
  columns.

- *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 10032 rows and 22 columns.

- *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
  rows and 21 columns.

- *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
  Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

- We hope that this project will serve as practice for carrying our your
  own *independent* data analysis. Remember to comment your code, be
  explicit about what you are doing, and write notes in this markdown
  document when you feel that context is required. As you advance in the
  project, prompts and hints to do this will be diminished - it’ll be up
  to you!

- Before choosing a dataset, you should always keep in mind **your
  goal**, or in other ways, *what you wish to achieve with this data*.
  This mini data-analysis project focuses on *data wrangling*,
  *tidying*, and *visualization*. In short, it’s a way for you to get
  your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: cancer_sample 2: building_permits 3: apt_buildings 4: vancouver_trees

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

``` r
### EXPLORE HERE ###
#steam_games
```

``` r
# Create function that uses dplyr to find three dimensions in a dataset

# The function here is used to avoid repetition and shorten the code, it is still using dplyr at its base

dimensions = function(dataframe = steam_games) {
  return(as.data.frame(dataframe %>% summarise(
    Number_Rows = n(),
    Number_Columns = length(names(dataframe)),
    Is_Data_Frame = is.data.frame(dataframe)
  )))
}
```

``` r
# Creates a data frame with three dimensions extracted using dplyr, it is saving the output into a new data frame and adding a column
# that stores the data frame's name, in this case that is 'cancer_sample'

cancer_sample_dimensions = dimensions(cancer_sample)

cancer_sample_dimensions['df_name'] = 'cancer_sample'
```

``` r
# Creates a data frame with three dimensions extracted using dplyr, it is saving the output into a new data frame and adding a column
# that stores the data frame's name, in this case that is 'building_permits'

building_permits_dimensions = dimensions(building_permits)

building_permits_dimensions['df_name'] = 'building_permits'
```

``` r
# Creates a data frame with three dimensions extracted using dplyr, it is saving the output into a new data frame and adding a column
# that stores the data frame's name, in this case that is 'apt_buildings'

apt_buildings_dimensions = dimensions(apt_buildings)

apt_buildings_dimensions['df_name'] = 'apt_buildings'
```

``` r
# Creates a data frame with three dimensions extracted using dplyr, it is saving the output into a new data frame and adding a column
# that stores the data frame's name, in this case that is 'vancouver_trees'

vancouver_trees_dimensions = dimensions(vancouver_trees)

vancouver_trees_dimensions['df_name'] = 'vancouver_trees'
```

``` r
# Here I am creating an empty data frame to store values from all four data frames and be able to see them together in the same df

df_dimensions_e = data.frame(
  Number_Rows = c(),
  Number_Columns = c(),
  Is_Data_Frame = c(),
  df_name = c()
)
```

``` r
# This code appends the values for each data frame and 

# The _e, _c, _d, _a notation is used so that if this code is rerun R doesn't continually append rows to a data frame already built


df_dimensions_c = rbind(df_dimensions_e, cancer_sample_dimensions)
df_dimensions_b = rbind(df_dimensions_c, building_permits_dimensions)
df_dimensions_a = rbind(df_dimensions_b, apt_buildings_dimensions)
df_dimensions = rbind(df_dimensions_a, vancouver_trees_dimensions)

df_dimensions %>%
  select(df_name, everything())
```

    ##            df_name Number_Rows Number_Columns Is_Data_Frame
    ## 1    cancer_sample         569             32          TRUE
    ## 2 building_permits       20680             14          TRUE
    ## 3    apt_buildings        3455             37          TRUE
    ## 4  vancouver_trees      146611             20          TRUE

``` r
colnames(cancer_sample)
```

    ##  [1] "ID"                      "diagnosis"              
    ##  [3] "radius_mean"             "texture_mean"           
    ##  [5] "perimeter_mean"          "area_mean"              
    ##  [7] "smoothness_mean"         "compactness_mean"       
    ##  [9] "concavity_mean"          "concave_points_mean"    
    ## [11] "symmetry_mean"           "fractal_dimension_mean" 
    ## [13] "radius_se"               "texture_se"             
    ## [15] "perimeter_se"            "area_se"                
    ## [17] "smoothness_se"           "compactness_se"         
    ## [19] "concavity_se"            "concave_points_se"      
    ## [21] "symmetry_se"             "fractal_dimension_se"   
    ## [23] "radius_worst"            "texture_worst"          
    ## [25] "perimeter_worst"         "area_worst"             
    ## [27] "smoothness_worst"        "compactness_worst"      
    ## [29] "concavity_worst"         "concave_points_worst"   
    ## [31] "symmetry_worst"          "fractal_dimension_worst"

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

> For me the cancer_sample feels like the most relevant to my previous
> work (being a student in the School of Population and Public Health).
> Additionally, when I looked at the names of the variables in the data
> frame. I noticed there is a “diagnosis” variable, which could be used
> as an interesting outcome for the analysis in this assignment.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

> In this case, I would be interested in knowing: are values for
> area_mean consistent across diagnositc groups? It is possible that the
> average area values vary between those that have a malignant tumor or
> not.

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if
    it makes sense)
3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…
6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!
7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

> 2.1.1 Plot the Distribution of a numeric variable
>
> *Solution*: Create a faceted plot in ggplot2 to visualize the
> distribution of a continuous variable.
>
> *Justification*: In this case, I am interested in seeing if the
> distribution for the variable “area_mean” is consistent across
> “diagnosed” categories.

``` r
# Here I am using geom_density to build a density plot for the variable "area_mean"
# The green line outlines where the mean value for the area_mean is in the overall distribution.

area_mean_plot = ggplot(cancer_sample, aes(x=area_mean))+
  geom_density()+
  geom_vline(aes(xintercept=mean(area_mean)),
             color="green", linetype="dotdash")

area_mean_plot
```

![](Mini-Projec-1_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

> 2.1.2 Create a new variable
>
> *Solution*: Take the log of area_mean and store results in a new
> variable using mutate.
>
> *Justification*: I previously noticed that the distribution for this
> variable is highly skewed. I want to create a new dummy variable that
> splits values for the skewed variable into (0) below the mean or (1)
> Above the mean. Binarizing this variable may be useful in future
> analysis.

``` r
# This code creates a new data frame called "cancer_sample_new_var" which contains all variables from the original "cancer_sample" plus
# The new variable computed using mutate.

# In this case, I am taking the log of all values in the area_mean column and storing those values in a new column called "log_area_mean"
# Using a logarithmic transformation is helpful when we have a highly skewed distribution, as is the case for area_mean
cancer_sample_new_var = cancer_sample %>%
  mutate(log_area_mean = log(area_mean))
```

``` r
# This code quickly creates a graph for the new varlues for the log_area_mean variable.
# Notice how the distribution looks more normal now even though there is a slight bump at the right side of the distribution.

ggplot(cancer_sample_new_var, aes(x=log_area_mean))+
  geom_density()+
  geom_vline(aes(xintercept=mean(log_area_mean)),
             color="green", linetype="dotdash")
```

![](Mini-Projec-1_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

> 2.1.3 Explore the relationship between 2 variables in a plot.
>
> *Solution*: create a scatterplot of log_area_mean(transformed variable
> created in 2.2.2) and area_worst
>
> *Justification*: from the name, it seems like both variables may be
> related conceptually. Plotting them together will help me see if they
> are colinear in any way.

``` r
# In this case, I created a simple scatterplot that had the original area_mean variable at the x-axis and area_worst values in the y-axis.

# In this case it looks like both variables are highly correlated, in future analysis potentially only one of the two could be used.

texture_smooth_scatter = ggplot(cancer_sample_new_var, aes(x=area_mean, y=area_worst))+
  geom_point()

texture_smooth_scatter
```

![](Mini-Projec-1_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->

> 2.1.4: Use a boxplot to look at the frequency of different
> observations within a single variable.
>
> *Solution*: create a boxplot in ggplot for the variance of
> log_area_mean.
>
> *Justification*: I am interested in visualizing the frequency of
> observations or whether there are any clear outliers in the
> log_area_mean column I created in 2.2.2. From the graph in 2.2.3 there
> seemed to be some heteroschedasticity after the ~1,500 value. I am
> curious to see if the boxplot will highlight any outliers.
> Additionally, I want to see if raw values for area_mean are different
> across diagnosis groups, hence I will use diagnosis in my x-axis.

``` r
# This code is creating a simple boxplot where the X-axis is diagnosis and y-axis are the raw values for area_mean.
# The line in the middle of the box indicates the median for theach group, values outside of the box are well above or below the 1st or 3rd quartiles.

area_mean_across_diagnosis = ggplot(cancer_sample_new_var, aes(x=diagnosis, y = area_mean))+
  geom_boxplot()

area_mean_across_diagnosis
```

![](Mini-Projec-1_files/figure-gfm/unnamed-chunk-15-1.png)<!-- -->

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

> *Comment*: In the past, I have worked with health-related data but not
> with cancer-specific datasets. I am excited to embark on a new project
> and learn more along the way. I wish, however, that I could have
> either (1) more information about the variables I have and how they
> were collected, or (2) to have more information of different types
> (e.g., when where the tests done, what age was the patient, what was
> their background, have they had any form of cancer before either
> themselves or their direct relatives). Still, given the data I have
> access to now, here are four questions I would like to explore
> further:
>
> *3.1*: There seem to be three forms of each “characteristic”. For
> example, there is a radius_mean, radius_se, and radius_worst. I am
> wondering if each form may have a different relationship to the
> “diagnosis” of each observation. For example, do higher values for
> radius_mean and radius_se correspond to higher odds of having a
> malignant tumor? Or do they have unique relationships with diagnoistic
> results?S
>
> *3.2*: I am also interested in understanding the relationship between
> sets of variables that seem to be related conceptually. It could be
> that smoothness and texture refer to similar concepts. So, I would
> like to know: is there any correlation between smoothness_mean and
> texture_mean across observations?
>
> *3.3*: I am curious about the difference between \_mean and \_worst
> variables (e.g., radius_mean vs radius_worst). I am curious if having
> a wider range between the \_mean and the \_worst values is also
> predictive of wether an observation has a malignant tumor.
>
> *3.4*: Ultimately, I am curious to see which factors are most
> predictive of a cancer diagnosis. I have seen that Random Forest can
> be used to estimate variable importance in prediction problems. I
> would like to know, which variables are the most predictive of a
> cancer diagnosis from the ones in the original dataset?

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

- In a sentence or two, explains what this repository is, so that
  future-you or someone else stumbling on your repository can be
  oriented to the repository.
- In a sentence or two (or more??), briefly explains how to engage with
  the repository. You can assume the person reading knows the material
  from STAT 545A. Basically, if a visitor to your repository wants to
  explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

- All Rmd files have been `knit`ted to their output md files.
- All knitted md files are viewable without errors on Github. Examples
  of errors: Missing plots, “Sorry about that, but we can’t show files
  that are this big right now” messages, error messages from broken R
  code
- All of these output files are up-to-date – that is, they haven’t
  fallen behind after the source (Rmd) files have been updated.
- There should be no relic output files. For example, if you were
  knitting an Rmd to html, but then changed the output to be only a
  markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
