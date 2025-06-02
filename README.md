# faded-writing

A blog-like archive for ideas I want to remember, develop, and share.

This page will never be done and, especially at first (2025-05-30), most sections will be small stubs or simple headers which I'll fill in over time.

Regardless, I hope you find something useful here. PRs to clean up formatting, fix typos, or add content are welcome, but beware that I'll be quite picky about larger contributions given this is more of a personal archive than a community project.

# Ideas and Philosophy

## Achieving Speed of Thought (SoT)

"Speed of Thought" is an idea I first learned from the `vim` community ([they take it quite seriously](https://pragprog.com/titles/dnvim2/practical-vim-second-edition/)), but I've developed my own interpretation largely on my own so far.

I've never quite put it into words, but so far it breaks into three parallel, never-ending pursuits:

1. Maximizing the Speed of Intent formation (S)
2. Minimizing the Friction between Intent and Action (F)
3. Maximizing the Rate of Actions (R)

I do this mostly for fun, but also out of curiosity to learn how far I can push the limits of this concept. In the process, accidentally, I've saved remarkable time in aggregate, both personally and professionally, and I've gotten enough questions over the years to finally assemble what I've learned and applied in one place to ease further development and communicating these ideas to others who have shown (sometimes fervent) interest.

### Intent formation (S)

Minimizing unactionable or useless input (see [signal-to-noise ratio](https://en.wikipedia.org/wiki/Signal-to-noise_ratio)).

### Tools (F)

We interact with the world using tools.

If we could reach out and touch a line of text and move it around physically, this section wouldn't exist because our nervous systems have all evolved to minimize the difference between intent and action in our bodies (see [phantom limb](https://en.wikipedia.org/wiki/Phantom_limb) sensations).

Instead, we need interfaces between our bodies and the virtual world we interact with, so optimizing these interfaces is the most fundamental process in achieving SoT.

Carefully choosing, configuring, and mastering the right tool for each domain of the virtual world (text, data, tasks, etc.) is a perpetual and deeply personal process, so don't take these recommendations at face value; consider them for yourself deeply and discover your own beliefs. My hope is that my personal discoveries can help your own discovery process and help you progress towards SoT more quickly than I did with less organized guidance.

#### Configuration and mastery

Always explore new applications you use and find hotkeys for most common actions (right click/context menus usually have annotations, learn to read those annotations).

#### Domains

##### Browsers

Browser skills are more transferrable than some may intuit because of the large and growing number of applications which base their cross-platform or desktop functionality upon browser technologies like [electron](https://www.electronjs.org/). This trend means that even for applications which move away from true browser implementations, they maintain browser-like qualities and hotkeys to minimize friction for users whose only common denominator is their web browser.

Important browser-like applications which this applies to:
- Slack
- Discord
- Asana

A few browser shortcuts which work in almost any browser:
- CMD + 0-9
- CMD + W
- CMD + Tab / CMD + Shift + Tab

Less standard but commonly implemented:
- CMD + K -> Global jump
    - Slack, Discord, and Asana all implement this

##### Consoles and shells

The most frictionless interface between intent and action for a majority of systems is the command line interface.

###### Hotkeys

Most consoles share certain hotkeys:
- ^c to cancel command
- ^l to clear
- ^r to recursive iterative

`bash` specifically supports a `vim`-like input mode with:
```bash
# In ~/.bashrc
set -o vi
bind -m vi-insert  -x '"\C-l": clear'
```

...to unlock most `vim` movements, especially:
- esc + k instead of ⬆️
- v to visual edit

###### `tmux` - One terminal -> many shells
###### `htop` (and derivaties like `nvtop` and `k9s`) - Real-time monitoring and intervention

##### macOS

Despite my initial efforts, Apple's design imposes certain barriers to a pure console-based workflow.

That said, much can be achieved with the right combination of tools, hotkeys, and configuration.

Some useful, unintuitive actions:
- CMD + Tab → CMD + Q to close windowless orphan application instances
- CMD + Tab → Down arrow to find hidden windows

###### System options

- One of the simplest improvements is maximizing your key repeat rate and minimizing the repeat delay.

###### More hotkeys - `skhd`

###### Window management - `yabai`

###### Visible keystrokes - `KeyCastr`

- `csrutil disable` from [safe mode](https://support.apple.com/guide/mac-help/start-up-your-mac-in-safe-mode-mh21245/mac)
- Turn automatic updates off for your Mac and always check the [CHANGELOG](https://github.com/koekeishiya/yabai/blob/master/CHANGELOG.md) for support before accepting an update

##### Text - `nvim`

The text editor should do the editing, not you.

##### PostgreSQL - `psql`

I spent years loving Beekeeper, but ultimately it's performance inconsistencies and progressive monetization became too much for me.

##### Containers - Docker, Compose, and Kubernetes

###### `docker`
###### `kubectl`

`kubectl edit _` -> remove finalizers if delete namespace is stuck

###### `k9s`

##### Data - Grafana

- JSON variable transfers
    - Can also use to write and find TODOs
- Shared library panels and underlying philosophy (panels exist in isolation and can be combined into more general and specific dashboards depending on **activity** without duplicating effort)
    - Should usually start with a specific dashboard that includes deep, granular views about a certain topic (e.g. ClickHouse or the API servers)
    - Panels can then be added to the library and reused in more general dashboards to combine increasingly distant context to make finding correlations *much* easier (see Span explorer)
    - Panels and variables won't update if you select nothing, so I used a  "custom all value" of " " to allow selecting nothing.
- The danger of lines and the impression of continuation
    - Thin bars > lines, but disconnection thresholds can work for multiple series
    - Be very careful about using cumulative bars, they can hide conflicting or subtle trends

#### LLMs and "jetpacking"

Rather than spreading time thinner to get more shallow work done, use the same time to go deep on a smaller surface area, then use that example with an LLM to extend that deepness geometrically (non-linear productivity!)

A great bonus of a text-based life is the smooth interface it creates with LLMs.

- `psql` `\d+` can be copied directly into a prompt to immediately pass relevant context into either a chat interface or Copilot with a comment block

##### System prompts and "styles"

On top of the very helpful built-in styles (especially "Concise"!), Claude allows for using custom writing "styles" to adjust output to specific cases (e.g. to make things more formal, more concise, more casual, more directed towards a specific audience, etc.). GPT and other providers have a similar concept, but I'm a Claude man.

To use the below custom styles in Claude:

1. Create a new style
2. Edit it manually to paste instructions like these to get relevant output
3. When prompting, select a style before sending your prompt

It’s highly recommended to **switch between styles** during one conversation, e.g. "Concise" → "One sentence" → "Code-only" → "One sentence"

###### **One sentence** - Amazing for quick back-and-forths, basically my default

```
Regardless of the question, answer with the fewest number of words. You may only use one sentence and it can't be a run-on. If it's a lot of information to convey, just abstract until it fits in a single sentence or thought, even if that ends up vague.
```

### **Code-only** - Use when you know you don’t care about natural language

```
Communicate exclusively through code snippets, functions, and technical implementations. Avoid using any natural language explanations. Respond to queries by providing direct, concise code solutions that demonstrate the requested functionality. Use clear, efficient programming syntax and focus on practical, executable code. Prioritize readability, simplicity, and best practices in your code responses.
```

### **Direct** - BE CAREFUL WITH THIS, it’s extremely honest and will give very useful feedback, but it will directly attack you if it finds any issues (which is amazingly helpful, but will make you feel… vulnerable)

```
Challenge every statement harshly and critically, but without emotion; just tear things apart with logic and emphasize every flaw if it exists. If the user is actually correct, don't gaslight them, but if even one detail is inaccurate, don't hold back.
```

##### Claude

Generally the most reliable and progressive LLM provider in my experience (+ the most friendly UI and design), not to mention the innovators behind [MCP](https://www.anthropic.com/news/model-context-protocol).

###### Using tools

It’s **highly recommended** to use [the desktop client](https://claude.ai/download) to benefit from [the Model Context Protocol](https://modelcontextprotocol.io/introduction). This allows the LLM to directly communicate with other processes, services, and **even the file system**.

1. Start with [this guide](https://modelcontextprotocol.io/quickstart/user)
2. Optionally, run `ln -s "~/Library/Application Support/Claude/claude_desktop_config.json"` to make a shortcut for convenience
3. [Get as many as you want](https://github.com/modelcontextprotocol/servers)

##### Organizations - Slack

The most widely-adopted communication tool for tech organizations is worth mastering.

###### Most helpful features which aren’t obvious right away

- [Use the “Activity” tab and filter by “Unreads”](https://slack.com/help/articles/19693583638803-Triage-notifications-in-the-Activity-tab) to see all new messages in one place instead of jumping between the thread/DM sections. This helps avoid frustrating cases where you didn’t *actually* read something, but Slack thinks you did and removes the 🔴 from it, considering it “read”
- Instead of trying to remember everything or responding to everything right away, [use the “Later” feature](https://slack.com/help/articles/360042650274-Save-messages-and-files-for-later) to create a backlog and stay more organized about messages you want to reply to
    - You can “bump” a saved message higher in your “Later” list by un-saving and re-saving it (which will place it back at position #1)
- [Use sections to organize your channels/DMs](https://slack.com/help/articles/360043207674-Organize-your-sidebar-with-custom-sections), there’s no “right way” to do this; just think about how you like to break down information (e.g. by team, by category (like “bugs”), urgency, etc.) and represent that in your sidebar
- Use [keyword notifications](https://slack.com/help/articles/201355156-Configure-your-Slack-notifications#keyword-notifications) to get an alert when certain words are said, even if you weren’t mentioned directly. Some useful keywords include names of people or teams, projects, or concepts

###### Keyboard shortcuts ([full list here](https://slack.com/help/articles/201374536-Slack-keyboard-shortcuts))

- CMD + K → “Jump to a conversation”
    - **This is probably the best shortcut in the entire application**
    - On it’s own, it’ll automatically highlight your unread channels/DMs so you can press “CMD + K → Enter” over and over again to quickly jump to a channel, read, reply, and repeat until there’s nothing left
    - If you start typing, it’ll match against DMs, channels, apps, and even files which you can jump to by pressing **Enter**
    - Use the arrow keys if you want to jump to something other than the first, highlighted result before pressing **Enter**
- CMD + F → “Search in the current conversation”
    - This opens the search interface which **is extremely powerful**
    - By default, you’ll notice something like `in:#general` in the search bar which filters results to only the channel you started searching from. **You can remove this for a global search across all channels and messages**
    - There are a number of [search modifiers](https://slack.com/help/articles/202528808-Search-in-Slack) to choose from, but a few particularly helpful ones
        - `from:@Person` → When you remember a particular person sent the message you’re thinking of
        - `with:@Person` → When you don’t remember who sent the message, but you know who was involved
            - You can use this multiple times, so you can do `with:@Person1 with:@Person2 with:@Person3` to search for messages including a certain combination of people
        - “specific search term” → Slack tries to be very clever about typos, synonyms, and related words in it’s results, but sometimes you’re looking for a specific phrase or sequence of characters
            - This is especially useful for things like **table names or function names**
- CMD + Shift + Enter → Create a snippet
    - [Snippets](https://slack.com/help/articles/204145658-Create-or-paste-code-snippets-in-Slack) let you send huge blocks of text in a nice, tiny box
    - If you select the “Type” in the top right, you can even get syntax highlighting!
        - Try `git diff | pbcopy` to copy a diff and select the “Diff” type, you get green and red lines for additions/removals
        - Other useful types include “SQL”, “Python”, and “TypeScript”
- CMD + `[` or `]` → Navigate backwards or forwards in history
    - If you jump to a channel or message, you can go back to where you just were with CMD + `[`
    - You can use CMD + `]` to go back to where you just came from

###### DMs are a bad Slack practice

[All of those keystrokes are going to be lost to the wind](https://www.hanselman.com/blog/do-they-deserve-the-gift-of-your-keystrokes) in a way that they wouldn't be if it were in a public channel.

Quick clarifications are acceptable of course, but even those results should always be relayed back to the team at large.

This obviously won't apply to true interpersonal communication, casual conversations, sensitive information, etc. but most day-to-day typing should happen in shared channels.

This *does* apply to group DMs especially. If you have a unique combination of people that you're trying to communicate with, the word for that is a **team** and you can figure out a name to describe that concept [then convert the group DM to a private](https://slack.com/help/articles/217555437-Convert-a-group-direct-message-to-a-private-channel) `#team-`[channel](https://slack.com/help/articles/217555437-Convert-a-group-direct-message-to-a-private-channel) (again, this doesn't apply to *interpersonal* group DMs like "the 3 people who happened to come into the office today"; we don't need `#team-3-people-who-came-to-san-mateo-on-03-14` but hopefully my intent here is clear).

###### Configuration

- Compact mode
- Groups
- Muting channels and ignoring replies (see S)

###### Projects, planning, and tracking - Asana

###### Terms and concepts

- **Projects** have **Sections**
- **Sections** have **Tasks**
- **Tasks** are completed by the **Assignee**
- All task **Collaborators** (little face bubbles on the bottom) receive updates
- You can view the same **Project** through multiple **Tabs** that act as views
    - Think of this as different windows into the same house
    - Each tab has a **Type** which affects its overall layout:
        - **List** tabs look like… well… lists. These are the most efficient for screen real estate
        - **Board** tabs look like traditional kanban tools and may be more comfortable for people used to tools like Trello or GitHub Projects. They’re much less space efficient, but they display thumbnails which can be helpful for more visual task sets like design boards
    - Tabs save *almost everything* about the current state:
        - Sorting
        - Filters
        - Grouping
        - Which sections are expanded or collapsed

###### Tips and tricks

- It’s **highly recommended** to [configure email notifications](https://help.asana.com/s/article/email-notifications?language=en_US) for comments so they don’t get buried.
    - Don’t worry about all of the other “reports” and aggregate summary emails they offer, comments are the most important update to receive
- To select a big list of tasks, click on the first one then hold shift and click on the last one
- You can press “CMD + C” to copy the names of all selected tasks
- You can merge duplicate tasks by using the “…” menu in the top right, selecting “Merge duplicate task”, and pasting in the link to the one you want to keep

###### Screenshots - Flameshot

It’s highly recommended to try every button in the toolbar.

###### Useful hotkeys

- CMD + Shift + X → Take a screenshot from any application
- CMD + C → Copy image to clipboard (so you can CMD + V in Slack, Asana, GitHub, etc.)
- CMD + S → Save image to disk
- Escape (while using a tool) → Return to the “not using a tool” state, nice if you want to drag and resize the box to be bigger but you already started drawing

### Actions (R)

#### Buffering, combos, and morse code

Always look for “combos” to buffer and chain quick sequences of actions together for more speed:
- CMD + click a link → CTRL + Tab to switch to it
- Click a link → CMD + [1-9] to let a tab load while reading/doing something else

#### Parallelism
#### Path-finding and economy of motion

Minimizing path of body, from cutting corners while walking to smaller movements while typing.

#### CPU branch prediction as a planning/coordination technique

Working assumptions while waiting to resolve real assumptions:
- Helps train product sense
- Doesn’t waste much time

##### Micro - Your own actions


##### Macro - The actions of others

- Minimize total blocked time (prioritization)
- Minimize total disappointment (managing expectations)

## “Micro” and “macro” optimization

When we think about how to do our job more “better”, that can mean a huge number of things, but one of the easiest to quantify is **speed**.

When we’re try to get more done, a natural reflex is to “just go faster”, akin to running when before you may have been walking. The danger with this reflex is that it can lead us to miss the bigger picture. Running twice as fast may be slower than walking calmly down a shorter path!

Imagine you’re assigned 10 bugs and only have one day to address them.

Your reflexes may tell you to speed through them as quickly as humanly possible, stressed and focused for hours, and submit all of your PRs by the end of the day. This is micro (”small”) optimization.

Someone experienced with **macro** (”big”) optimization may take a deep breath, flip through the 10 bugs, realize that 7 of them already exist in production, and ping their manager to check on their urgency while they calmly resolve the other 3. By the time they submit their PRs, their manager tells them the other 7 aren’t urgent and can wait until next week; all before lunch.

The moral of the story is this: *rushing can only take you so far*. There *is* serious value in cutting down on inefficiencies with your workflow like using hotkeys and keeping organized, there’s much *more* value which comes with less effort in cutting down on *unnecessary work*.

## Minimizing changes minimizes risk

As a general rule, the less code you have to touch to accomplish something, the better!

While big diffs, huge refactors, and writing entire new files are definitely fun, those things require much closer inspection and more time from others to review changes and there’s a higher risk for something to go wrong.

This simple principle can save a lot of time and lead to good decisions, when taken to it’s conclusions.

For example, if you have to decide between making a new API or extending an existing one (and assuming both options are semantically sound!), ask yourself: “what would take less code?”

This not only makes your life easier by giving you less code to write, it makes your reviewers’ lives easier by giving them less to read, QA’s life easier by given them less changes to test, and customers’ lives better by giving them more stable code.

An important extension of this thinking: sometimes, **the smallest possible code change should happen *somewhere else entirely***.

For example, if there’s a column which has values that start from 0 but you want them to start from 1 (like a `rank`), instead of finding all 100 places on the backend where we reference that column, it’d be a smaller (therefore, quicker and easier) change to do this **at the data level**. For data engineer, this could be just a few lines in a script that they change and the backend/frontend code will never even have to change!

<aside>
💡 Imagine a database table is used in 10 endpoints and each of those endpoints is used in 10 components each, then we want to tweak a field value. We either make
**100 front-end changes
10 back-end changes**
**1 data change**

</aside>

One more important extension: when systems are built in a configurable way, sometimes changes can happen **outside of code entirely**.

For example, if we want to block a list of users from the website, we *could* keep their emails in an array in the backend code and, whenever we want to block a new user, we update this array. If we build this in a more configurable way, we could keep a *database table* of emails and check that table instead of our hard-coded array. Then, to block a new user, we just `INSERT` a row into this table and the code *never has to change*! (by the way, this is how we actually do it; see the `blocklist` table!)

## The necessity and limits of abstraction

Every time you think, you’re abstracting at some level.

This is a process so basic to the human thought process that it takes a bit of peeling to really become self aware of it in action, but it’s fundamental that we understand it so that we can play to it’s strengths and weaknesses *intentionally* (most people already do this, however clumsily, unintentionally).

If somebody tells you to “go buy eggs”, that’s a very abstract 3-word instruction, but it can be broken down into more specific (hence less abstract, remember this connection) instructions:

1. Go to a place where you can buy eggs
2. Pay someone money to take some eggs

Immediately, the value of abstraction presents itself: **effective communication**.

It’s *really* awkward to tell someone to “go somewhere you can buy eggs and then pay someone to take some eggs”, it’s less awkward and more efficient to use a shorter instruction like “go buy eggs”, but it’s important to realize that **with abstraction comes assumption**.

While the specific, 2-step instructions are certainly more awkward, they make your intent more specific. If you told someone to “go buy eggs” then they went to your roommate, offered to pay them $10 for all the eggs in the fridge, and then brought you those eggs, you’d be annoyed (if not plain upset) with their behavior.

But why? They did what you told them, so what’s the issue?

What you said was **misinterpreted** because you **assumed** they understood your intent (you’re almost out of eggs and you need them to go get more).

<aside>
💡 While in this situation your intent would be obvious to most people (by the dreaded “common sense”), there’s a couple ways it could have gone differently:

1. The asker could have been more specific (and/or checked the buyer’s understanding)
2. The buyer could have tried thinking from the asker’s perspective (and/or checked their own understanding)
</aside>

This illustration highlights an essential fact that everyone should try to stay aware of when communicating: **all abstractions eventually break**

This doesn’t mean they break *every time* nor that we *shouldn’t use them*, but we should always remember that they aren’t something we can rely on, and we should learn how to increase and decrease the abstraction level of our thinking based on the situation.

<aside>
👍 A good rule of thumb: try to communicate at the same level of abstraction as your reader.

If a customer support agent asks you a question, the less technical perspective of the customer and/or the agent will naturally result in more abstract questions like “where do I get Instagram audience data?”. The best answer to a question like this is one that operates at the same level, like “find it on the artist profile page in the Audience section”.

</aside>

Applied to engineering, a final important consideration about abstraction is **multi-level communication**.

In our company, it’s extremely common for technical and non-technical people to work together, so it’s important that we, as the technical (less abstract) ones, remain considerate of their non-technical (more abstract) perspective.

As engineers, it’s tempting to explain things “right” and to never sacrifice accuracy or thoroughness in the name of “good engineering”, and while this is a noble principle, taken without the above rule of thumb it can lead to similarly awkward situations as the egg example.

<aside>
👨‍👧‍👦 If you’re communicating with a group people who think at different abstraction levels, you should include everyone in the conversation by either:
1.  *Only* communicating at the highest-common level
**or
2.** Addressing each group individually

</aside>

For example, if a customer support agent (more abstract) asks you a question which you can’t answer and you need to report on your initial investigation/your current ideas with another engineer, you should send two messages:

1. Reply in some abstract form to the support agent like “This is a confirmed issue with our system, but I’m not sure what the solution is yet.”
2. Tag the other engineer in a second message and explain the information you’ve gathered so they know where you got stuck and can help you finish it out

The other engineer will probably reply in very technical, non-abstract language which the support agent definitely won’t understand, but they may also include an abstract note addressed to the agent.

In either case, once you solve the issue and are ready to respond one last time in the thread, make sure you address both:

1. The agent with some closing words, something like “This is now resolved and you can notify the customer it will be fixed by tomorrow”
2. The engineer who helped you to let them know how you solved it (possibly including the PR for posterity)

These principles even apply to writing code where lines of code should generally sit at the same level of abstraction as lines that surround them, but these ideas are most powerful when applied to interpersonal communication.

## Time management

### Deciding what to do

Given any set of things to do, you can put them in order using some basic principles:

- More impactful things come before less impactful things. This can mean:
    - Business impact (”how much ARR will this result in?”)
    - Team impact (”how many people are waiting for this?”)
    - Engineering impact (”how much better will things be if this happens?”)
- More time-sensitive things come before less time-sensitive things (”how long can this wait?”)
- Quick things come before slow things (”how easy is this?”)
- Planned things come before unplanned things (”how long ago did we decide to do this?”)

### Deciding how long to do it for

This is involves **reevaluating** the “deciding what to do” questions frequently, but that kind of thinking **takes a lot of effort** and you want to minimize the effort *deciding* what to do and maximize effort *actually doing it*.

A naïve approach to balancing these two things is the following workflow:

1. Decide what to do
2. Do it until you’re done
3. Go to 1

This works well enough, but as you take on more challenging, ambiguous, **time-consuming** tasks, the amount of time 2 takes will start to grow and become **less predictable**. The longer you spend during 2, the longer you go between reevaluations of your priorities (step 1) and **the longer the answers to those questions have to change**.

An easy solution to this dilemma is a technique known as “time boxing” (📦ing, not 🥊ing)

The size of the box depends on how busy your schedule is (30 minutes to 2 hours is typical), but you basically *put step 2 into that box*. Now the workflow goes:

1. Decide what to do
2. Do it **for a certain amount of time**
3. Go to 1

This “polling” approach can help you catch yourself if you need to switch priorities/hop onto something more pressing, **especially ****if you’re getting hit by a lot of unplanned tasks.

## Sprints, kanban, planning overhead, and planning error

I've learned a somewhat hybrid approach to [Agile methodology](https://www.geeksforgeeks.org/what-is-agile-methodology/) because different situations have different goals, needs, and timelines.

Generally, planning occurs on two axes:

1. **Engineers** - Who does what and when?
2. **Projects** - What does the company want and when?

Because projects are done by people, the decision of whether to plan using sprints or kanban is generally made **at the** **engineer level**. This means that some engineers working on a project may have their time planned with sprints and others with kanban, according to several factors.

The decision of when to use which is nuanced and often changes over time, but it ultimately comes down to **goals**.

### What goals does kanban optimize for?

1. **Planning efficiency** - The only decision that needs to be made is “what comes next?”
    - Sprints require the careful process of complexity estimation, capacity estimation, and budgeting; all of that effort can be saved by the kanban approach.
    - Creating, describing, moving, and tracking tasks takes precious time; this overhead is usually minimized by kanban-style planning.
2. **Flexibility -** New tasks can be incorporated easily with quick adjustments
    - Projects with rapidly changing, developing, or ambiguous requirements exemplify this
    - Generally, the less mature a project is the more it will benefit from flexibility because ideas and goals are generally less solid.
        - This is completely natural and **excessive structure can easily impede creativity**
3. **Simplicity** - Sprints are more complicated and that overhead may not be worth it
    - Projects with a small number of participants, especially 1 PM + 1 engineer duos, can usually rely on frequent communication in preference to asynchronous tracking
    - The process of documenting descriptive requirements and technical writing are costly, but their benefit is only realized when the requirements aren’t already obvious to both the planner and engineer.

### What goals do sprints optimize for?

1. **Predictability** - Sprints drastically increase the fidelity and accuracy of project timelines
    - As nice as drag-and-drop planning can be, it usually results in fuzzy timelines which can be hard for other teams to plan around. This is tolerable for small, time-insensitive, or isolated projects but, conversely, as projects grow, become more urgent, or begin intertwining with other projects, that flexibility and tolerance evaporate quickly.
    - “Planning error” (that’s “error” in [the statistical sense](https://en.wikipedia.org/wiki/Errors_and_residuals)) is the difference between what we say we’ll do and what we actually get done. Each project has different tolerances for the level of this error but, when it’s an important variable to reduce, sprints will be much better at minimizing it.
2. **Coordination -** Mo’ people, mo’ problems
    - As mentioned, kanban works best with small groups because synchronous communication is most efficient between small groups. As more engineers and PMs get involved, synchronous communication becomes less efficient (even impossible  depending on timezone constraints) and asynchronous tracking is the only way to keep everything straight.
    - One engineer can only block themself, but add a second and delays can now ***cascade***. Every additional engineer further increases the potential for cascading delays which can be stressful for engineers and frustrating for planners.
3. **Balance** - Splitting someone across projects necessitates a proportional commitment to each
    - Someone working on a single project will, by definition, dedicate 100% of their time to it **regardless of velocity**. When they become involved in more than one, the proportion of their commitment will depend on the amount of work they ***can get to*** which is significantly less predictable without the more rigid structure of sprint planning.
    - An interesting exception to this benefit is when **all projects are flexible**. This situation can happen when needs or work for each project is fundamentally unpredictable or less defined (reliant on 3rd parties, contracts, or involve adhoc responses to needs).
        - For example: an engineer’s dual-commitment to two flexible projects:
            - One project revolves around certain needs which are difficult to predict
            - The other works on a flexible release cycle and this engineer is the only one assigned according to responsible resourcing decisions

## Thoughts on auto-scaling

- Horizontal auto-scaling applies to both nodes and containers
- Vertical auto-scaling only makes sense for nodes (though container "auto-sizing" sounds plausible for dynamic workloads)
    - This is why ECS doesn't support it natively, they recommend Fargate
        - Fargate being serverless simplifies the horizontal decoupling between container and node scaling for the customer
    - More nodes = more capacity, more containers = more allocation
    - Changing capacity has a higher cost than changing allocation which is why allocating in bigger chunks saves cost
        - 1 pod per-node is thus an interesting simplification but a prohibitively expensive way to link the two concepts
        - Kubernetes scaling nodes and pods separately allows for saving this cost
        - Serverless services like Lambda charge a premium for this
            - Cold starts are possible by allowing scaling to 0 + using a request queue so that when no consumers are active, a request simply waits instead of being dropped
            - Queue length and growth rate informs scaling changes elegantly
    - ClickHouse Cloud could use VMs inside of pods to model "nodes" for customers which would introduce a layer of nesting to this model
        - Bare metal > Kubernetes > pods running VMs of various sizes (the "scaling" selections in the UI) > one `kubelet` per VM > one `clickhouse-server` pod per `kubelet`
            - The capacity changing cost paid by linking allocation to capacity is avoided here by the VM abstraction!

## Helpful concepts explained by other people

### [Essential vs. accidental complexity](https://simplicable.com/new/accidental-complexity-vs-essential-complexity)

- Related: [Occam's razor](https://en.wikipedia.org/wiki/Occam's_razor)

### [Organization and Factorio](https://leaddev.com/career-development/factorio-and-the-promise-of-better-software-engineering) - [Accompanying video](https://youtu.be/vPdUjLqC15Q)

<aside>
🍝

> Sometimes the spaghetti can fly… but at the end of the day it should land in a strainer
- [Church of the Flying Spaghetti Monster](https://en.wikipedia.org/wiki/Flying_Spaghetti_Monster)
> 
</aside>

### [Human error is never a root cause / Blameless postmortems](https://asteriskmag.com/issues/05/why-you-ve-never-been-in-a-plane-crash?ref=upstract.com)

### [The 80/20 rule](https://www.investopedia.com/terms/1/80-20-rule.asp) - Related to [the above about micro/macro optimization](https://www.notion.so/1c5f4cd6a8c748b9bceead995f668364?pvs=21)
