---
layout: post
title:  "Ordinal Regression is Hard"
date:   2023-12-14
categories: 
permalink: "/:categories/:title"
---


Often the language and notation used when talking about ordinal regression 
can be off-putting. The goal is obvious--- evaluate the effect of 
a set of variables on an ordinal outcome(where the categories have inherent order)
---but the execution is not.

Many resources I have come across maybe throw some notation at you, 
words like *proportional odds*, and then go straight into some code where 
they tell you how to interpret the output. On the surface this is fine, 
you come out the other end with a specific library to use and how 
to word your results, but I don't think this leads to a good understanding of what ordinal 
regression does. 

## An Example

Learning by doing works very well as a primer for topics in my experience, so 
instead of talking about theory we are going to solve a problem, and 
along the way learn a little about how an ordinal regression model works.

### The Undergrads Strike Back 

> You are a researcher studying the effect of two compounds on plant growth...

Your experiment is as follows: plants are grown in the same type of soil containing 
different concentrations of either compound, and you want to see how the 
concentration of each compound affects plant height. You give 6 plants 
compound A and 6 plants compound B, with 2




{% highlight stan %}

data {
  int<lower=1> Ncan; // Number of candidates
  int<lower=1> Nrev; // Number of reviewers
  int<lower=1> Nobs; // Number of nonmissing observations
  int<lower=1> Nk; // Number of discrete scores
  
  
  array[Nobs] int obs_scores; // Observed discrete scores
  array[Nobs] int can_ID; // Candidate ID
  array[Nobs] int rev_ID; // Reviewer ID
}

{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[MASS-r]: https://cran.r-project.org/web/packages/MASS/index.html


