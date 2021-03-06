---
title: Plot variants programmatically 
keywords: 
last_updated: Wed Jun  1 20:48:34 2016
---

The following plots a selected variant with `ggbio`.


{% highlight r %}
library(ggbio)
mychr <- "ChrC"; mystart <- 11000; myend <- 13000
args <- systemArgs(sysma="param/bwa.param", mytargets="targets.txt")
ga <- readGAlignments(outpaths(args)[1], use.names=TRUE, param=ScanBamParam(which=GRanges(mychr, IRanges(mystart, myend))))
p1 <- autoplot(ga, geom = "rect")
p2 <- autoplot(ga, geom = "line", stat = "coverage")
p3 <- autoplot(vcf[seqnames(vcf)==mychr], type = "fixed") + xlim(mystart, myend) + theme(legend.position = "none", axis.text.y = element_blank(), axis.ticks.y=element_blank())
p4 <- autoplot(txdb, which=GRanges(mychr, IRanges(mystart, myend)), names.expr = "gene_id")
png("./results/plot_variant.png")
tracks(Reads=p1, Coverage=p2, Variant=p3, Transcripts=p4, heights = c(0.3, 0.2, 0.1, 0.35)) + ylab("")
dev.off()
{% endhighlight %}

![](systemPipeVARseq_files/plot_variant.png)
<div align="center">Figure 3: Plot variants with programmatically.</div>

