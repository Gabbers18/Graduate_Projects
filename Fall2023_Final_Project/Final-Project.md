# Introduction

#### Big Research question

Does meditation influence an individual’s selective attention?

#### Source

The dataset I will be using corresponds to this journal article: Heino,
M. T. (2022). Cognitive Dynamics of a single subject: 1428 Stroop tests
and other measures in a mindfulness meditation context over 2.5 years.
Journal of Open Psychology Data, 10. <https://doi.org/10.5334/jopd.51> I
found this dataset on Open Science Framework.

#### Description

The data was collected independently by a 33-year old male doctoral
student. Each row represents one day of data collection over the course
of 900 days.

I am particularly interested in the following measured variables:

- Stroop_congruent\_ pre_meditation: Stroop test consisted of 5
  congruent (e.g. the word “blue” in blue letters) and 15 incongruent
  trials. This is the average response time (in units of 1/100 seconds)
  to the congruent trials before doing the meditation.
- Stroop_incongruent\_ pre_meditation: Stroop test consisted of 5
  congruent and 15 incongruent (e.g. the word “yellow” in red letters)
  trials. This is the average response time (in units of 1/100 seconds)
  to the incongruent trials before doing the meditation.
- Stroop_congruent\_ post_meditation: Stroop test consisted of 5
  congruent (e.g. the word “blue” in blue letters) and 15 incongruent
  trials. This is the average response time to the congruent trials
  after doing the meditation.
- Stroop_incongruent\_ post_meditation: Stroop test consisted of 5
  congruent and 15 incongruent (e.g. the word “yellow” in red letters)
  trials. This is the average response time to the incongruent trials
  after doing the meditation.
- Meditation_randomised_walking: Meditation was randomised to be
  performed as walking meditation. 1 for yes, 0 for no.
- Meditation_randomised_sitting: Meditation was randomised to be
  performed as sitting meditation. 1 for yes, 0 for no.
- Meditation_randomised_standing: Meditation was randomised to be
  performed as standing meditation. 1 for yes, 0 for no.
- Clarity_pre_meditiation: Answer, on a scale of 1-10 in intervals of
  0.25, to the question “How clear do you feel right now”.
- Clarity_post_meditation: Answer, on a scale of 1-10 in intervals of
  0.25, to the question “How clear do you feel right now”.
- Calm_pre_meditation: Answer, on a scale of 1-10 in intervals of 0.25,
  to the question “How calm do you feel right now”.
- Calm_post_meditation: Answer, on a scale of 1-10 in intervals of 0.25,
  to the question “How calm do you feel right now”.

# Research Question 1

## Does meditation moderate an individual’s selective attention over time?

### How did I come up with this question?

- Previous research has indicated that meditation has the potential to
  improve selective attention
- Attention Control Theory: meditation allows for one to focus on
  specific stimuli while ignoring distractions

### Why should you care?

- Most psychological research is conducted using larger sample sizes
- This question puts this theory to the test using a single individual
- Incorporate meditation as a method to instill focus
- Potential long-term positive consequences

<!-- -->

    ## Warning: Removed 112 rows containing missing values (`geom_line()`).

![](Final-Project_files/figure-gfm/clean-data-line-graph-1.png)<!-- -->

### Let’s disect this:

- August of 2014-February 2017
- No change in selective attention on the Stroop test over time
- These results are consistent regardless of the type (pre, post,
  congruent, or incongruent).

<!-- -->

    ## `summarise()` has grouped output by 'year_month'. You can override using the
    ## `.groups` argument.

![](Final-Project_files/figure-gfm/average-months-1.png)<!-- -->

### Let’s disect this

- There is a steady decline in average Stroop test response times
- Trend is present across all Stoop Test types
- We might infer this is due to consistent meditation over the months

# Model 1 - Stroop Test Congruent Pre-meditation

    ##                  Estimate   Std. Error     t value  Pr(>|t|)
    ## (Intercept)  1.005573e+01 7.357570e-02 136.6718398 0.0000000
    ## date        -4.731375e-07 2.340746e-06  -0.2021311 0.8398717

    ## [1] 5.705955e-05

- weak, negative correlation
- small r-squared value

# Model 2 - Stroop Test Incongruent Pre-meditation

    ##                  Estimate   Std. Error     t value Pr(>|t|)
    ## (Intercept)  1.028054e+01 6.704583e-02 153.3360301 0.000000
    ## date        -1.229204e-06 2.133004e-06  -0.5762785 0.564608

    ## [1] 0.0004636075

- weak, negative correlation
- small r-squared value

# Model 3 - Stroop Test Congruent Post-meditation

    ##                  Estimate   Std. Error     t value  Pr(>|t|)
    ## (Intercept)  1.031213e+01 7.522098e-02 137.0910857 0.0000000
    ## date        -1.231186e-06 2.383356e-06  -0.5165764 0.6056132

    ## [1] 0.0003767664

- weak, negative correlation
- small r-squared value

# Model 4 - Stroop Test Incongruent Post-meditation

    ##                  Estimate   Std. Error     t value  Pr(>|t|)
    ## (Intercept)  1.051242e+01 6.884847e-02 152.6893109 0.0000000
    ## date        -4.942518e-07 2.181445e-06  -0.2265708 0.8208229

    ## [1] 7.250086e-05

- weak, negative correlation
- small r-squared value

### Let’s disect this

- linear model to show the relationship between time taken on a test
  based on the date
- decrease in time taken to complete stroop test over time
- relationship is prevalent regardless of test type and time of
  meditation
- all of the relationships between the type of stroop test and point in
  time (date) are weak and negatively correlated

# Research Question 2

## How do different types of meditation moderate an individual’s selective attention over time?

### How did I come up with this question?

- Attention regulation theory: discusses that meditation may influence
  selective attention
- Sitting meditation may contribute to improvements on selective
  attention
- little research indicating if walking or standing meditations may
  affect selective attention

### Why should you care?

- Compare results across the three (sitting, standing, and walking)
- may be useful in selecting the appropriate type of meditation to
  directly promote selective attention

<!-- -->

    ## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'

    ## Warning: Removed 26 rows containing non-finite values (`stat_smooth()`).

    ## Warning: Removed 26 rows containing missing values (`geom_point()`).

![](Final-Project_files/figure-gfm/congruent-performance-1.png)<!-- -->

### Let’s disect this

- decrease in stroop congruent test completion times across standing and
  walking meditations
- sitting meditation completion times decrease, then level out over time
- potentially a larger increase in selective attention over time for
  standing and walking meditations compared to sitting meditations

<!-- -->

    ## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'

    ## Warning: Removed 27 rows containing non-finite values (`stat_smooth()`).

    ## Warning: Removed 27 rows containing missing values (`geom_point()`).

![](Final-Project_files/figure-gfm/incongruent-performance-1.png)<!-- -->

### Let’s disect this

- incongruent plot displays similar trends to the previous plot
- decrease in stroop congruent test completion times across standing and
  walking meditations
- sitting meditation completion times decrease, then level out over time
- potentially a larger increase in selective attention over time for
  standing and walking meditations compared to sitting meditations

# Research Question 3

## How does meditation affect average daily mood over time?

### How did I come up with this question?

- Theories behind modulating one’s Default Mode Network (DMN) may result
  in feelings of calmness and clarity
- Modulating one’s DMN can be achieved through meditation.

### Why should you care?

- We have all probably heard that meditation is good at clearing one’s
  head
- Is this apparent within an individual’s data?

<!-- -->

    ## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'

    ## Warning: Removed 14 rows containing non-finite values (`stat_smooth()`).

    ## Warning: Removed 14 rows containing missing values (`geom_point()`).

![](Final-Project_files/figure-gfm/rq3-1.png)<!-- -->

### Let’s disect this

- decrease in variability over time between average mood ratings
- may be as a result of consistent meditation
- spread is lessened over time

<!-- -->

    ## `summarise()` has grouped output by 'year_month'. You can override using the
    ## `.groups` argument.

    ## `geom_smooth()` using method = 'loess' and formula = 'y ~ x'

![](Final-Project_files/figure-gfm/graph-average-monthly-1.png)<!-- -->

### Let’s disect this

- Similar trends as the previous plot
- Little change in moods over time
- This is a single individual’s data
