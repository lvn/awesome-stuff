# Awesome Stuff
Curated list of miscellaneous stuff that will probably eventually help me.

## Systemsy Stuff
A very incomplete mishmash of occasionally-hard-to-separate stuff about operating systems, databases, distributed systems, etc. I also have a [blog](http://blog.elvinyung.com/) where I talk about this kind of stuff.

### General Databases
* [Readings in Database Systems](http://www.redbook.io/) - aka *the* red book (for databases, not the other one), new and in website form. Awesome introductory readings on databases.
* [Architecture of a Database System](http://db.cs.berkeley.edu/papers/fntdb07-architecture.pdf)
* [The Gamma Database Machine Project](http://pages.cs.wisc.edu/~dewitt/includes/paralleldb/ieee90.pdf) - popularized -- but did not introduce -- the concepts of sharding, and hash join algorithms.

### DHTs
DHTs are different from databases because they generally assume a much more decentralized environment, but they're important for understanding some techniques used by modern distributed databases.

* [Chord: A Scalable Peer-to-peer Lookup Service for Internet Applications](http://pdos.csail.mit.edu/papers/chord:sigcomm01/chord_sigcomm.pdf) - 
* [Kademlia: A Peer-to-peer Information System Based on the XOR Metric](https://pdos.csail.mit.edu/~petar/papers/maymounkov-kademlia-lncs.pdf)

### "NoSQL" Systems
* [Dynamo: Amazon’s Highly Available Key-value Store](http://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf) - The original NoSQL datastore. Uses a bunch of really neat tricks. Inspiration for Riak and Cassandra, and a bunch of others.
* [Bigtable: A Distributed Storage System for Structured Data](http://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf) - The *other* original NoSQL datastore. Bigtable is interesting mainly because of its single-machine I/O optimizations.
* [Megastore: Providing Scalable, Highly Available Storage for Interactive Services](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/36971.pdf) - a database built on top of Bigtable. It is probably better known in the form of [Google Cloud Datastore](https://cloud.google.com/datastore/docs/concepts/overview).
  * Also see [Spanner: Google’s Globally-Distributed Database](https://static.googleusercontent.com/media/research.google.com/en//archive/spanner-osdi2012.pdf), which has a general design that's clearly inspired by Megastore, but has a bunch of interesting techniques. It literally uses atomic clocks to do multi-version concurrency control.

### "Big data"
* [The Google File System](http://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf) - an early example of a modern distributed file system. 
* [MapReduce: Simplified Data Processing on Large Clusters](https://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce-osdi04.pdf) - A very simple abstraction for doing large-scale data processing. 
* [Resilient Distributed Datasets: A Fault-Tolerant Abstraction for In-Memory Cluster Computing](http://www-bcf.usc.edu/~minlanyu/teach/csci599-fall12/papers/nsdi_spark.pdf) - an abstraction that improves over (and subsumes) MapReduce in a few ways. It is probably more well-known as the core of a system called [Spark](http://spark.apache.org/).

### Consensus
* [The Part-Time Parliament](http://research.microsoft.com/en-us/um/people/lamport/pubs/lamport-paxos.pdf) - Leslie Lamport's super confusing paper on the Paxos protocol.
* [Paxos Made Simple](http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf) - A somewhat simpler to understand paper on the same topic, by the same author.
* [Paxos Made Live - An Engineering Perspective](http://www.cs.cmu.edu/~15-440/READINGS/paxos-made-live.pdf) - Google's experiences building [Chubby](https://static.googleusercontent.com/media/research.google.com/en//archive/chubby-osdi06.pdf), and why Paxos is so hard in real life.
* [In Search of an Understandable Consensus Algorithm](https://raft.github.io/raft.pdf) - introduced Raft, a consensus algorithm that seems to be becoming more popular than Paxos.

### Distributed Transactions
* [Calvin: Fast Distributed Transactions for Partitioned Database Systems](http://cs.yale.edu/homes/thomson/publications/calvin-sigmod12.pdf) 
* [MaaT: Effective and scalable coordination of distributed transactions in the cloud](http://www.vldb.org/pvldb/vol7/p329-mahmoud.pdf)

### Operating Systems
* [Operating Systems: Three Easy Pieces](http://pages.cs.wisc.edu/~remzi/OSTEP/) - Very nice introductory to operating systems stuff, with good coverage of new technology. The whimsical tone makes it a fun read. Better than [the Dinosaur Book](https://www.amazon.ca/Operating-System-Concepts-Abraham-Silberschatz/dp/1118129385) in my opinion.
* [Showstopper!](https://www.amazon.com/Show-Stopper-Breakneck-Generation-Microsoft/dp/0029356717) - About the development of Windows NT. Given the amount of computing analogies, I think this is intended for a nontechnical audience. Still a great read regardless, with lots of insight into various OS design decisions.

### Cluster Management
* [The Datacenter as a Computer](http://web.eecs.umich.edu/~mosharaf/Readings/DC-Computer.pdf)
* [The Datacenter Needs an Operating System](https://cs.stanford.edu/~matei/papers/2011/hotcloud_datacenter_os.pdf) - Zaharia et al. makes a very good case for why we need OS-like functionality for large clusters of machines.
* [Mesos: A Platform for Fine-Grained Resource Sharing in the Data Center](https://people.eecs.berkeley.edu/~alig/papers/mesos.pdf) - Also by Zaharia et al.; introduced the idea of a two-level datacenter scheduler.
* [Large-scale cluster management at Google with Borg](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43438.pdf) - Unbeknownst to everyone, Google has had a datacenter operating system for more than a decade. This is the precursor to the open-source [Kubernetes](https://kubernetes.io/).
* [Omega: flexible, scalable schedulers for large compute clusters](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/41684.pdf) - documents a project that attempted to replace Borg. Interestingly, this was published *before* the Borg paper.
* [The Chubby lock service for loosely-coupled distributed systems](https://static.googleusercontent.com/media/research.google.com/en//archive/chubby-osdi06.pdf) - describes how Google does metadata storage for distributed systems.

### Misc.
* [The Night Watch](https://www.usenix.org/system/files/1311_05-08_mickens.pdf) by James Mickens

## Architecture
This section has some overlap in terms of coverage with the *Systems* sections above, but is more focused on a real-life software engineering persepctive.

* [Architecture of Open Source Applications](http://aosabook.org/en/index.html) - Contains short chapters on the architectures of various open source software.
* [ZeroMQ - The Guide](http://zguide.zeromq.org/page:all) - Good intro to messaging patterns and ZeroMQ.
* [Scaling Pinterest](https://www.youtube.com/watch?v=jQNCuD_hxdQ)
* [How We've Scaled Dropbox](https://www.youtube.com/watch?v=PE4gwstWhmc)
* [Facebook and Memcached](https://www.youtube.com/watch?v=UH7wkvcf0ys)
* [Storage Systems at a Rapidly Scaling Startup with a Small Team](https://www.youtube.com/watch?v=bLyv8zKa5DU) - A story from Data@Scale of how Instagram scaled their datastores.
* [Zookeeper Resilience at Pinterest](http://engineering.pinterest.com/post/77933733851/zookeeper-resilience-at-pinterest) - How Pinterest implements ZooKeeper for service discovery.
* [How Does a Relational Database Work?](http://coding-geek.com/how-databases-work/)
* [Why You Should Never Use MongoDB](http://www.sarahmei.com/blog/2013/11/11/why-you-should-never-use-mongodb/)
* [Enterprise Integration Patterns](http://www.enterpriseintegrationpatterns.com/toc.html) - General primer on distributed messaging.
* [Adventures in message queues](http://antirez.com/news/88)
* [Learn to stop using shiny new things and love MySQL](https://engineering.pinterest.com/blog/learn-stop-using-shiny-new-things-and-love-mysql) by Marty Weiner - Great advice about technology decisions for a startup/new product, especially on where you should put your data.
* [TAO: The Power of the Graph](https://www.facebook.com/notes/facebook-engineering/tao-the-power-of-the-graph/10151525983993920) - on Facebook's distributed graph-oriented datastore.
* Dropbox's [Edgestore](https://www.youtube.com/watch?v=VZ-zJEWi-Vo)

## Machine Learning
* [Composing Music With Recurrent Neural Networks](http://www.hexahedria.com/2015/08/03/composing-music-with-recurrent-neural-networks/)
* [Machine Learning is Way Easier Than It Looks](https://blog.intercom.io/machine-learning-way-easier-than-it-looks/)
* [Machine Learning is Fun](https://medium.com/@ageitgey/machine-learning-is-fun-80ea3ec3c471)

## Startups
* [Good and Bad Reasons to Become an Entrepreneur](https://medium.com/i-m-h-o/good-and-bad-reasons-to-become-an-entrepreneur-decf0766de8d) by Dustin Moskovitz
* [Founders at Work](http://www.amazon.com/Founders-Work-Stories-Startups-Early/dp/1430210788) by Jessica Livingston et al. - Collection of interviews with various tech entrepreneurs.
* [Secrets of the Rockstar Programmers](http://www.amazon.com/Secrets-Rock-Star-Programmers-Riding/dp/0071490833) by Ed Burns et al. - Interviews of software experts.
* [Zero to One](http://www.amazon.com/Zero-One-Notes-Startups-Future/dp/0804139296) by Peter Thiel - notes from Peter Thiel's Startups class at Stanford.
* [The Hard Thing About Hard Things](http://www.amazon.com/The-Hard-Thing-About-Things/dp/0062273205) by Ben Horowitz - on the unglamorous parts of running a company.
* [Viral Loop](http://www.amazon.com/Viral-Loop-Facebook-Businesses-Themselves/dp/1401323499) by Adam L. Penenberg - How successful tech startups grow virally.
* [Once You're Lucky, Twice You're Good](http://www.amazon.com/Once-Youre-Lucky-Twice-Good/dp/1592404278) by Sarah Lacy - A look at the startup world just before the 2008 crisis.
* [What’s Your Hour in ‘Silicon Valley Time’?](https://medium.com/backchannel/how-the-tech-press-forces-a-narrative-on-companies-it-covers-5f89fdb7793e) - explains the concept of Silicon Valley Time, i.e. stages of a tech startup.
* [Startup Product Development](http://www.slideshare.net/MarketingNinja/startup-product-development)
* [Are "Better" Ideas More Likely to Succeed? An Empirical Analysis of Startup Evaluation ](http://www.hbs.edu/faculty/Publication%20Files/16-013_201e071c-9dd8-4838-b5aa-492f4f202822.pdf)
* [Work Hard, Live Well](https://medium.com/life-learning/work-hard-live-well-ead679cb506d) by Dustin Moskovitz
* [Early Excite History](http://www.slideshare.net/ryanmcintyre/early-excite-history) by Ryan McIntyre - slides on the history of Excite. Has some discussions near the end about why Google survived and Excite didn't.
* [Meta-Programming: A Software Production Method](https://www.parc.com/content/attachments/meta-programming-csl-76-7.pdf) by Charles Simonyi - a paper on organizing software developers for productivity.
* [Three Stories](http://justinkan.com/three-stories) by Justin Kan

## Product
* [How to Build Great Products](http://www.defmacro.org/2013/09/26/products.html) - A blog post on identifying good features to build for a product, and how to allocate resourcces. 
* [10x not 10%](https://library.gv.com/10x-not-10-34ba4eb91130#.dd0g6v2tc)

## Career
* [Breakout Career Notes](http://www.breakoutcareers.com/) - Collections of career tips from tech entrepreneurs and VCs.
* [Pmarca Guide to Career Planning](http://pmarchive.com/guide_to_career_planning_part0.html) - Career guide from Marc Andreesen.
* Google's [Guide for Technical Development](https://www.google.com/about/careers/students/guide-to-technical-development.html)

## Mildly Interesting
* [Brian Bi on K&R C](https://spin0r.wordpress.com/2014/11/21/kr-c/) - Blog post about early installment weirdness in the C language.
* [Codepen Thing](http://codepen.io/erucipe/full/vNKzJw/) - A really awesome visualization of a Fourier transform.

## Blogs
* [Paul Graham](http://www.paulgraham.com/) - founder of YC and Viaweb.
* [Jamie Zawinski](http://www.jwz.org/blog/) - well-known Netscape/Mozilla engineer.
* [Jacques Mattheij](http://jacquesmattheij.com/) - cool stuff about tech
* [Evan Miller](http://www.evanmiller.org/) - guy writes about applied math, programming languages, random tech stuff...
* [Ben Horowitz](http://www.bhorowitz.com/) - one half of a16z.
* [Purple Motes](http://purplemotes.net/) - Interesting stuff from history

## Random
* [The Codeless Code](http://thecodelesscode.com/contents) - Zen koans, but for software development.
* [Bay Area to Standard American English Translator](http://www.mcsweeneys.net/articles/bay-area-to-standard-american-english-translator) 
