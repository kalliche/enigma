---
id: lifetimes-of-cryptographic
title: Lifetimes of cryptographic
permalink: inv/lifetimes-of-cryptographic.html
---
# Lifetimes of cryptographic hash functions

I've written some cautionary articles on using cryptographic hashes to create content-based addresses (compare-by-hash). This page brings together everything I've written and keeps an updated table of the status of popular cryptographic hash functions.

Quick summary of my recommendations on compare-by-hash: **If you are using compare-by-hash to generate addresses for data that can be supplied by malicious users, you should have a plan to migrate to a new hash every few years**. For example, BitTorrent falls into this category, but rsync doesn't. Keep in mind that new, more secure hashes are likely to have larger outputs (e.g., 256 bits for SHA-2 vs. 160 bits for SHA-1) and be more computationally expensive.

An Analysis of Compare-by-hash appeared in Hot Topics in Operating Systems 2003 The original paper casting doubt on compare-by-hash as the answer to all of life's problems.

The code monkey's guide to cryptographic hash functions appeared in LinuxWorld Practical advice for programmers, plus the chart of popular hash function lifetimes (reproduced below).

<div class="md-div-center">
<img alt="imagen" src="{{ site.baseurl }}/img/tabla.png" class="md-img md-center">
</div>

[1] Note that 128-bit hashes are at best 2^64 complexity to break; using a 128-bit hash is irresponsible based on sheer digest length.
[2] What happened in 2004? Xiaoyun Wang and Dengguo Feng and Xuejia Lai and Hongbo Yu happened.
[3] Google spent 6500 CPU years and 110 GPU years to convince everyone we need to stop using SHA-1 for security critical applications. Also because it was cool.
[4] In 2007, the NIST launched the SHA-3 competition because "Although there is no specific reason to believe that a practical attack on any of the SHA-2 family of hash functions is imminent, a successful collision attack on an algorithm in the SHA-2 family could have catastrophic effects for digital signatures." One year later the first strength reduction was published.
The Hash Function Lounge has an excellent list of references for most of the dates. Wikipedia now has references to the rest.

<div class="md-div-center">
<img alt="imagen" src="{{ site.baseurl }}/img/tabla1.png" class="md-img md-center">
</div>

<a href="http://valerieaurora.org/hash.html" target="_blank">*Fuente investigativas*</a>
