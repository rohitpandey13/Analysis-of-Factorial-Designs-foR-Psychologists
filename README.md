
<img src='logo/BGUHex.png' align="right" height="139" />

# Analysis of Factorial Designs foR Psychologists

<sub>*Last updated 2020-04-18.*</sub>

This Github repo contains all lesson files used in the graduate-level
course: *Analysis of Factorial Designs foR Psychologists - Practical
Applications in R*, taught at Ben-Gurion University on the Negev (spring
2019 semester). This course assumes basic competence in R (importing,
regression modeling, plotting, etc.), a long the lines of the
prerequisite course, *Advanced Research Methods foR Psychologists*,
which can be found
[here](https://github.com/mattansb/Advanced-Research-Methods-foR-Psychologists).

The goal is to impart students with the basic tools to fit and evaluate
**statistical models for factorial designs (w/ plots) using
[`afex`](https://afex.singmann.science/)**, and and conduct **follow-up
analyses (simple effects, planned contrasts, post-hoc test; w/ plots)
using [`emmeans`](https://cran.r-project.org/package=emmeans)**.
Although the focus is on ANOVAs, the materials regarding follow-up
analyses (\~80% of the course) are applicable to linear mixed models,
and even regression with factorial predictors.

**Notes:**

  - This repo contains only materials relating to *Practical
    Applications in R*, and does not contain any theoretical or
    introductory materials.  
  - Please note that some code does not work *on purpose*, to force
    students to learn to debug.

## Setup

You will need:

1.  A fresh installation of [**`R`**](https://cran.r-project.org/)
    (preferably version 3.6 or above).
2.  [RStudio](https://www.rstudio.com/products/rstudio/download/)
    (optional - but I recommend using an IDE).
3.  The following packages, listed by lesson:

| Lesson                                                                                                  | Packages                                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [01 ANOVA made easy](/01%20ANOVA%20made%20easy)                                                         | [`tidyr`](https://CRAN.R-project.org/package=tidyr), [`afex`](https://CRAN.R-project.org/package=afex), [`emmeans`](https://CRAN.R-project.org/package=emmeans), [`ggplot2`](https://CRAN.R-project.org/package=ggplot2), [`ggbeeswarm`](https://CRAN.R-project.org/package=ggbeeswarm)                                                                                                                               |
| [02 ANCOVA](/02%20ANCOVA)                                                                               | [`afex`](https://CRAN.R-project.org/package=afex)                                                                                                                                                                                                                                                                                                                                                                     |
| [03 analyzing interactions](/03%20analyzing%20interactions)                                             | [`dplyr`](https://CRAN.R-project.org/package=dplyr), [`afex`](https://CRAN.R-project.org/package=afex), [`emmeans`](https://CRAN.R-project.org/package=emmeans), [`AMCP`](https://CRAN.R-project.org/package=AMCP), [`ggplot2`](https://CRAN.R-project.org/package=ggplot2)                                                                                                                                           |
| [04 custom contrasts and effect sizes](/04%20custom%20contrasts%20and%20effect%20sizes)                 | [`afex`](https://CRAN.R-project.org/package=afex), [`emmeans`](https://CRAN.R-project.org/package=emmeans), [`effectsize`](https://CRAN.R-project.org/package=effectsize), [`dplyr`](https://CRAN.R-project.org/package=dplyr)                                                                                                                                                                                        |
| [05 assumption check and non-parametric tests](/05%20assumption%20check%20and%20non-parametric%20tests) | [`afex`](https://CRAN.R-project.org/package=afex), [`permuco`](https://CRAN.R-project.org/package=permuco), [`emmeans`](https://CRAN.R-project.org/package=emmeans), [`car`](https://CRAN.R-project.org/package=car), [`lmerTest`](https://CRAN.R-project.org/package=lmerTest), [`qqplotr`](https://CRAN.R-project.org/package=qqplotr), [`ggplot2`](https://CRAN.R-project.org/package=ggplot2)                     |
| [06 multiple comparisons and Bayesian ANOVA](/06%20multiple%20comparisons%20and%20Bayesian%20ANOVA)     | [`dplyr`](https://CRAN.R-project.org/package=dplyr), [`afex`](https://CRAN.R-project.org/package=afex), [`BayesFactor`](https://CRAN.R-project.org/package=BayesFactor), [`bayestestR`](https://CRAN.R-project.org/package=bayestestR), [`patchwork`](https://CRAN.R-project.org/package=patchwork), [`ggplot2`](https://CRAN.R-project.org/package=ggplot2), [`emmeans`](https://CRAN.R-project.org/package=emmeans) |

You can install all the packages used by running:

    # in alphabetical order:

    pkgs <- c(
      "afex", "AMCP", "BayesFactor", "bayestestR", "car", "dplyr",
      "effectsize", "emmeans", "ggbeeswarm", "ggplot2", "lmerTest",
      "patchwork", "permuco", "qqplotr", "tidyr"
    )

    install.packages(pkgs, dependencies = TRUE)

The package versions used here:

    ##          afex          AMCP   BayesFactor    bayestestR           car 
    ##      "0.27-2"       "1.0.0"  "0.9.12-4.2"       "0.5.3"       "3.0-7" 
    ##         dplyr    effectsize       emmeans    ggbeeswarm       ggplot2 
    ## "0.8.99.9002"       "0.3.0"       "1.4.5"       "0.6.0"       "3.3.0" 
    ##      lmerTest     patchwork       permuco       qqplotr         tidyr 
    ##       "3.1-2"       "1.0.0"       "1.1.0"       "0.0.4"       "1.0.2"
