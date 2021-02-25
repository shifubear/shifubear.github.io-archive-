---
layout: single
title:  "Faithful Reconstruction"
date:   2020-01-17 12:00:00 +0900
categories: ["Research", "Computational geometry"]
tags: ["Research", "Computational geometry"]
---

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      jax: ["input/TeX", "output/HTML-CSS"],
      tex2jax: {
        inlineMath: [ ['$', '$'], ["\\(", "\\)"] ],
        displayMath: [ ['$$', '$$'], ["\\[", "\\]"] ],
        processEscapes: true,
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code']
      }
      //,
      //displayAlign: "left",
      //displayIndent: "2em"
    });
  </script>
  <script src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML" type="text/javascript"></script>
  

How does a computer "see" an object? It turns out that this is a challenging question to answer, and there are many different approaches in resolving this problem. A sort of "no free lunch" scenario occurs when translating between existing representations, where ones that are cheaper to store in memory come with a lot of data loss, and vice versa. 

As I work on the diamonds problem, I have been reading a lot of literature on surface reconstruction. Generally, when a computer scans a real world object, the computer 'looks' at the object from many different angles and samples a set of points on the surface, and stores the object as a point cloud in memory. This point cloud doesn't have any topological or geometric information about the original object, which gives rise to the problem of surface reconstruction. In this problem, the goal is to use this set of points to create a model in the computer that represents the geometric and topological information as correctly as possible. 

The notion of correctness is vague here and there are many different ways to interpret the term depending on the application. Possibly as an objection to this vagueness, there have been attempts at formally defining a good surface reconstruction. Among these, one that's particularly grabbed my attention is the definition of a <u><strong>faithful reconstruction</strong></u>, introduced by Cheng et al.

## Definition 

<u><strong>Faithful Reconstruction</strong></u>: Let $P$ be an $\epsilon$-sample of a two-manifold $\Sigma$ in $\mathbb{R}^3$. A faithful reconstruction $T$ is a set of triangulated surfaces with vertices in $P$ that satisfy the following properties: 

1. $$T$$ is homeomorphic to $$\Sigma$$;
2. The Hausdorff distance between $$T$$ and $$\Sigma$$ is $$O(\epsilon)$$; 
3. For every triangle $$\tau$$ in $$T$$ and for every vertex $$p$$ of $$\tau$$, the normal of $\tau$ makes an $$O(\epsilon)$$ angle with $$\mathbf{n}_p$$. 
