---
layout: post
title:  "Java Syntax"
date:   2014-04-08
categories: java7
---

2-1 Is an example of an interface:

Listing 2-1. The Average interface
{% highlight ruby %}
public void setInts(int[] ints);
public float getAverage();
}
{% endhighlight ruby %}


Listing 2-2. The AverageImpl class
{% highlight ruby %}
package com.apress.java7forabsolutebeginners.syntaxExample;

public class AverageImpl extends Object implements Average {
  private long begin;
  private long end;
  private int[] ints;
  private static final String EXCEPTION_MESSAGE =
     "ints must contain at least one int";

public AverageImpl(int[] ints) throws IllegalArgumentException {
  if (ints.length == 0){
    throw new IllegalArgumentException(EXCEPTION_MESSAGE);
  }
  this.ints = ints;
}

@Override
public float getAverage() {
  begin = System.nanoTime();
  int result = 0;
  for (int i = 0; i < ints.length; i++) {
    result += ints[i];
  }
  end = System.nanoTime();
  return (float) result / ints.length;
}

public static float averageTwoNumbers(int a, int b) {
  return (float) (a + b) / 2;
}

// a classic getter method
@Override
public int[] getInts() {
  return ints;
}

// a classic setter method
@Override
public void setInts(int[] ints) throws IllegalArgumentException {
  if (ints.length == 0){
    throw new IllegalArgumentException(EXCEPTION_MESSAGE);
   }
   this.ints = ints;
 }

public long getRunTime() {
   return end - begin;
 }
}


{% endhighlight ruby %}




Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
