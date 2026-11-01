## Hi, I'm Hammad Qaiser.

I'm a human. It seems worth saying these days.

I study Computer and Information Sciences at PIEAS in Islamabad. I'm interested in security for LLM agents, multi-agent decision-making, and machine learning that runs in production. Currently, most of my time goes into one question: how do you let
AI agents trade without letting them anywhere near the money?

### SlashAgents: A policy kernel for LLM agents

In the 1970s, early computers let every program touch all of memory, so one bad program could take down the machine. Computing only
scaled once a kernel separated programs from what they could touch. Most AI agents today are back in that era: an LLM holds a signing key or an execution tool, guarded by a prompt. SlashAgents moves the models to user space. I call it the Ring 0 moment for autonomous finance.

A few LLM agents look at crypto markets, argue with each other about whether to trade, and pass their best idea to a
Rust program I wrote. The Rust program checks it against limits the user signed with their own wallet, and usually it
says no. Of 78 decisions so far, 81% were rejected or put on hold. The agents have opinions. They don't have the keys.

I built it this way because an LLM holding a signing key is one sneaky sentence away from emptying a wallet. So I tried
the sneaky sentences myself: 57 prompt-injection attacks, fed to a model I had deliberately broken. None of them got an
order past the limits.

It has made 50 real transactions on Hyperliquid (48 on testnet, 2 on mainnet). You don't have to believe me: every one
is on [Hyperliquid's public explorer](https://app.hyperliquid-testnet.xyz/explorer/address/0xB251AaA073e13009c58472ae3Ac91D7b19da7b28).
The code is private, but [slashagents-overview](https://github.com/hammadqaiser/slashagents-overview) explains how it
works.

Is it profitable? Not yet. Right now it's mostly very good at not trading.

### Other things I've made

- **[A serial-number reader for tractors](https://github.com/hammadqaiser/alphanumeric-character-and-digit-classifier-for-ESP32-CAM-and-Android)**:
  an ESP32-CAM photographs a stamped number on farm machinery and a phone reads it, with no internet. My first model
  scored 2.78%. There are 36 characters, and 1 in 36 is 2.78%, so I had trained a very expensive random guess. The
  culprits were a preprocessing bug and a pooling layer that threw away where the strokes were. The fixed model gets
  92.56%.
- **[Amaan CIRO](https://github.com/hammadqaiser/amaan-ciro)**: crisis response for Islamabad, for the day the flood and
  the heatwave arrive together.
- **[HIWMA chatbot](https://github.com/hammadqaiser/hiwma-chatbot)**: answers questions about solid waste management
  from six engineering textbooks, with citations, so nobody has to read the six textbooks.
- **[SlashMCP](https://github.com/hammadqaiser/slashmcp-multiagent-tool-execution-and-quant-server)**: gives agents real
  market numbers and risk checks, so they stop doing maths in their heads I built it as a test version of the private SlashMCP, and I no longer maintain it.

I also built the back office a courier company runs on every day. That one is private too, but people would notice if
it broke.

### Tools

Python and Rust most days, TypeScript for the web, and SQL, C/C++ and Java when needed. Linux, systemd, NATS, Temporal
and Cloudflare Workers to keep things running. PyTorch and TensorFlow Lite for models. EIP-712, Hyperliquid and Foundry
on chain.

### Say hi

hammadqais2@gmail.com · [LinkedIn](https://www.linkedin.com/in/hammadslash) · Islamabad, Pakistan

<sub>Written by me, not by my agents. They aren't allowed near the README either.</sub>
