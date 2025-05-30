# faded-writing

A blog-like archive for ideas I want to remember, develop, and share.

This page will never be done and, especially at first (2025-05-30), most sections will be small stubs or simple headers which I'll fill in over time.

Regardless, I hope you find something useful here. PRs to clean up formatting, fix typos, or add content are welcome, but beware that I'll be quite picky about larger contributions given this is more of a personal archive than a community project.

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

##### Organizations - Slack

The most widely-adopted communication tool for tech organizations is worth mastering.

###### Configuration

- Compact mode
- Groups
- Muting channels and ignoring replies (see S)

###### Hotkeys

- CMD + Enter -> Snippet

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
