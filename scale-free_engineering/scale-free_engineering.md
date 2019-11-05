# Scale-free Engineering

<!-- This is a set of thoughts regarding what happens when we strip the need for scale away from our engineering by design. -->

Engineers are obsessed with scale. 

By and large, I suppose this is because the money in engineering largely comes
from being able to draw small amounts of money from lots of users, thus turning
a profit. Our bread and butter isn't so much making programs, as making programs
that can remain resilient and performant in many different conditions. There are
lots of approaches to making this happen, but I think everyone's approaching
this from some angle or another at the end of the day, if they're really pulling
their weight.

This drives some of the most interesting results in modern computing, too. For
example: the CAP theorem, loosely defined, states that in a large (i.e.
scale-able, networked database) you can only have two of Consistency,
Availability, and Partition Tolerance as traits of your database. Respectively,
we mean up-to-date information, delivered quickly, and under dodgy network
conditions. Loosely defined.

Giving up partition tolerance is especially scary. If you don't care about
timeliness, or don't care about whether your data is very up-to-date, you can
give one of these up — big business cares a lot about the ability to suddenly
take on a lot more, though. Being able to partition, and partition safely, means
that a lot more users won't rock the boat too much; you can just throw more
virtual machines at a problem and call it a day, partitioning your workload
against a greater amount of resources.

We might give up partition tolerance for a couple of reasons. The most obvious
that comes to mind is that we really really need very timely information, that's
absolutely up-to-date. This essay posits a specific reason, though:
partition-tolerance is an example of something that only realistically matters
at scale, and when we discard scale-ability as a design choice, many computing
problems become easier in both technical and social ways.

## The Technical
