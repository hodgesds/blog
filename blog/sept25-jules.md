# A Look at My Recent Open Source Contributions with Jules

It's been a busy couple of months in my open source world, and I wanted to share a little bit about what I've been working on. I also had some help from my AI software engineering assistant, Jules, in putting this blog post together, and I'll talk a bit about how that worked.

### What I've Been Hacking On: `sched-ext/scx`

My main focus recently has been on the `sched-ext/scx` project, which is a framework for writing custom CPU schedulers for the Linux kernel. It's a fascinating project that allows for rapid prototyping and development of scheduling policies in BPF.

My contributions have been centered around improving the `scx_p2dq` scheduler, which stands for "Scheduler for P-cores with Dispatch Queues". Here's a breakdown of the key changes I've made:

*   **LLC Sharding:** I introduced a mechanism to shard the Last Level Cache (LLC). On systems with many CPUs sharing the same LLC, this helps to reduce contention and improve performance by grouping CPUs into separate dispatch queues.
*   **Overload Scheduling:** I added logic to handle system overload more gracefully. When all CPUs are busy, the scheduler can now make more intelligent decisions about where to place tasks. This involved refactoring the idle CPU selection logic and cleaning up some of the underlying data structures.
*   **Bug Fixes and Refinements:** Along with the larger features, I also made several smaller fixes and improvements, such as ensuring the "overloaded" flag is correctly unset and fixing idle CPU selection on single-LLC systems.

Overall, these changes should lead to better performance and stability for the `scx_p2dq` scheduler. For a complete set of changes, you can check out the major releases on the [sched-ext/scx GitHub releases page](https://github.com/sched-ext/scx/releases).

### How this Post Was Generated with Jules

This blog post was generated with the help of Jules, an AI software engineering assistant. I asked Jules to create a blog entry summarizing my recent open source work.

The process was a collaboration:

1.  **Initial Prompt:** I started by asking Jules to pull my latest commits from my GitHub profile and summarize my work from the last two months.
2.  **Data Gathering:** Jules first tried to use the GitHub API's public events endpoint, but ran into some authentication issues. After a few attempts, Jules found a way to list my public repositories and then fetch the commit history for each one.
3.  **A Change of Direction:** Initially, Jules identified a couple of my personal repositories that had recent commits. However, I wanted to focus on my work on `sched-ext/scx`, so I gave Jules a new instruction to look at that specific repository.
4.  **Commit Analysis:** Jules then fetched the commit history for `sched-ext/scx`, filtered for my commits from the last two months, and created the summary you see above.
5.  **Drafting the Post:** Finally, Jules drafted this blog post based on the summarized commits and the story of our interaction.

It was an interesting experience to see how Jules navigated the challenges of fetching the data and adapting to my feedback. It's a great example of how AI assistants can help with tasks beyond just writing code.
