---
layout: post
title:  "Ordinal Regression is Hard"
date:   2023-11-20
categories: 
permalink: "/:categories/:title"
---

Imagine you are a researcher who is interested in the effect of a drug on the levels of a specific 
biomarker in the blood. You 

$$ x^2 + 1 = 3y^4 $$

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
