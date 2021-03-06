---
title: Homework 5
keywords: 
last_updated: Sat Apr 23 15:51:22 2016
---

## Reverse and complement of DNA

__Task 1__: Write a `RevComp` function that returns the reverse and complement of a DNA sequence string. Include an argument that will allow to return only the reversed sequence, the complemented sequence or the reversed and complemented sequence. The following R functions will be useful for the implementation: 


{% highlight r %}
x <- c("ATGCATTGGACGTTAG")  
x
{% endhighlight %}

{% highlight txt %}
## [1] "ATGCATTGGACGTTAG"
{% endhighlight %}

{% highlight r %}
x <- substring(x, 1:nchar(x), 1:nchar(x)) 
x
{% endhighlight %}

{% highlight txt %}
##  [1] "A" "T" "G" "C" "A" "T" "T" "G" "G" "A" "C" "G" "T" "T" "A" "G"
{% endhighlight %}

{% highlight r %}
x <- rev(x) 
x
{% endhighlight %}

{% highlight txt %}
##  [1] "G" "A" "T" "T" "G" "C" "A" "G" "G" "T" "T" "A" "C" "G" "T" "A"
{% endhighlight %}

{% highlight r %}
x <- paste(x, collapse="")
x
{% endhighlight %}

{% highlight txt %}
## [1] "GATTGCAGGTTACGTA"
{% endhighlight %}

{% highlight r %}
chartr("ATGC", "TACG", x) 
{% endhighlight %}

{% highlight txt %}
## [1] "CTAACGTCCAATGCAT"
{% endhighlight %}

__Task 2__: Write a function that applies the `RevComp` function to many sequences stored in a vector.

## Translate DNA into Protein

__Task 3__: Write a function that will translate one or many DNA sequences in all three reading frames into proteins. The following commands will simplify this task:


{% highlight r %}
AAdf <- read.table(file="http://faculty.ucr.edu/~tgirke/Documents/R_BioCond/My_R_Scripts/AA.txt", header=TRUE, sep="\t") 
AAdf[1:4,]
{% endhighlight %}

{% highlight txt %}
##   Codon AA_1 AA_3 AA_Full AntiCodon
## 1   TCA    S  Ser  Serine       TGA
## 2   TCG    S  Ser  Serine       CGA
## 3   TCC    S  Ser  Serine       GGA
## 4   TCT    S  Ser  Serine       AGA
{% endhighlight %}

{% highlight r %}
AAv <- as.character(AAdf[,2]) 
names(AAv) <- AAdf[,1] 
AAv
{% endhighlight %}

{% highlight txt %}
## TCA TCG TCC TCT TTT TTC TTA TTG TAT TAC TAA TAG TGT TGC TGA TGG CTA CTG CTC CTT CCA CCG CCC CCT CAT 
## "S" "S" "S" "S" "F" "F" "L" "L" "Y" "Y" "*" "*" "C" "C" "*" "W" "L" "L" "L" "L" "P" "P" "P" "P" "H" 
## CAC CAA CAG CGA CGG CGC CGT ATT ATC ATA ATG ACA ACG ACC ACT AAT AAC AAA AAG AGT AGC AGA AGG GTA GTG 
## "H" "Q" "Q" "R" "R" "R" "R" "I" "I" "I" "M" "T" "T" "T" "T" "N" "N" "K" "K" "S" "S" "R" "R" "V" "V" 
## GTC GTT GCA GCG GCC GCT GAT GAC GAA GAG GGA GGG GGC GGT 
## "V" "V" "A" "A" "A" "A" "D" "D" "E" "E" "G" "G" "G" "G"
{% endhighlight %}

{% highlight r %}
y <- gsub("(...)", "\\1_", x) 
y <- unlist(strsplit(y, "_")) 
y <- y[grep("^...$", y)] 
AAv[y] 
{% endhighlight %}

{% highlight txt %}
## GAT TGC AGG TTA CGT 
## "D" "C" "R" "L" "R"
{% endhighlight %}

## Homework submission
Submit the 3 functions in one well structured and annotated R script to the instructor. The script should include instructions on how to use the functions.

## Due date

This homework is due on Thu, April 21th at 6:00 PM.

## Homework Solutions

See [here](https://drive.google.com/file/d/0B-lLYVUOliJFWlBhb2xNOWdfS0U/view?usp=sharing)


