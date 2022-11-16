# Review

## Info

Reviewer Name: Jerry 

Paper Title: PUMP: Architectural Support for Software-Defined Metadata Processing

## Summary
This paper introduces a new hardware framework for tagging memory and enforcing security polices 
based on those tags. It runs on RISC CPUs and tag each word(64B) with a pointer sized tag(64B).
With the tags set, the security policy programmer could write polices to be evaluated on each instruction. 
They also optimized it with opgroups, tag compression, tag translation, and miss handler acceleration.

### Problem and why we care
As the attack on system/software keep evolving, new kind of attack come out every day. We want to create
a framework for security operators to write security polices so that they can prevent the attacks.
We want to efficiently support fine-grained, software-defined metadata propagation without placing a visible, 
hard bound on the number of bits allocated to metadata or a bound on the number of policies simultaneously enforced

### Gap in current approaches
Currently, it's hard to implement security polices without a high overhead. Although we can use software to
define a security polices, the overhead is too high. Intel proposed hardware for bounds checking and isolation,
but they can only prevent a limited set of attacks.


### Hypothesis, Key Idea, or Main Claim
Associates a metadata tag with every word in the system’s main memory, caches, and registers. And enforce polices
based on those tags. Create rule cache to cache the result of a policy on certain tag patterns.

### Method for Proving the Claim 
Proposed four typical security polices and implemented them with the PUMP framework.

### Method for evaluating
- Benchmarking the CPU performance and CPU area & energy consumption.

### Contributions: what we take away
This paper introduces a very flexible and high-performance framework for tagging the memory in the operating system. 


## Pros (3-6 bullets)
- Universal framework that could be used to implement all kinds of security polices.
- Fast -- with hardware caches, most instructions could be done in single CPU cycle 
-  
## Cons (3-6 bullets)
- Trade off security with performance and memory - do we really need that?
- For security experts: is it necessary to implement all these security features with the framework? 
- Requires the security experts to thoroughly understand the software they are trying to protect and write 
policy for them.
- Less portability: once installed, never removable. 
### What is your analysis of the proposed?

Summarize and justify what your evaluation of the paper is. 

## Details Comments, Observations, Questions
### Discuss Questions:
- Why we want implement PUMP in hardware, instead of the software? What's the pros and cons here?
- What’s other possible novel Polices we could think of using PUMP?
- If you’re a security advisor in a company, would you adopt this security method? Why?

