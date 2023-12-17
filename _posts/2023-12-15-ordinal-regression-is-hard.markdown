---
layout: post
title:  "Ordinal Regression is Hard"
date:   2023-12-15
categories: 
permalink: "/:categories/:title"
---


Often the language and notation used when talking about ordinal regression 
can be off-putting. The goal is obvious--- evaluate the effect of 
a set of variables on an ordinal outcome(where the categories have inherent order)
---but the execution is not.

Many resources I have come across throw some notation at you, 
words like *proportional odds*, and then go straight into some code where 
they tell you how to interpret the output. On the surface this is fine, 
you come out the other end with a specific library to use and how 
to word your results, but I don't think this leads to a good understanding 
of what ordinal regression does. 

## Learning by Doing

Jumping right into a project works very well as a primer for topics in my experience, 
you may be more likely make to mistakes(because you have little idea what you are doing), 
but that is just part of learning! So instead of learning theory in a 
vacuum, we are going to encounter a problem and along the way learn about the 
structure of an ordinal regression model.

### The Problem

> You are a researcher studying the effect of two compounds on plant growth...

Your experiment is as follows: plants are grown in soil containing 
different concentrations of either compound, and you are interested in how the 
dose of either compound affects plant height after 5 days. The concentrations 
range from 0 to 1M with 5 levels(0.00M, 0.25M, 0.50M, 0.75M, 1.00M), and you 
have included triplicates where 3 plants are grown for each concentration. 
At the end of your experiment you measure plant height in cm for 27 plants, 
with 3 being controls given neither compound.

Unfortunately, a student in your lab has thoughtlessly decided to group 
your continuous height observations into 5 discrete categories: very short, 
short, medium, tall, and very tall. They do not remember the scale they 
used to make these categories, and have accidentally overwritten the 
previous dataset. You are now left asking the question "how can I 
infer the efficacy of each drug now?"

You had some domain knowledge about your variables before--- you 
assumed that plant height for a single dose is roughly normally distributed 
and the compounds have an additive effect on plant height ---but
how can you apply this information when everything has been discretized?

The solution is to think about how the data was generated. 
There was some continuous random variable(plant height) that followed all of 
the rules above. Only later was it grouped into discrete bins, so if 
we were to visualize the variable before the 

<div style="text-align: center;">
  <iframe src="assets/the_problem_f1.html" width="700" height="400"></iframe>
</div>


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

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[MASS-r]: https://cran.r-project.org/web/packages/MASS/index.html


