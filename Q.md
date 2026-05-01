外面文件夹~/Zai/team的teams应该是用不着了对吧？因为其实已经在.data中持久化了， 外面的~/Zai/team是原有的部分， 但是已经过时了我的理解通信中可能没用到不需要这部分？我需要详细知道现在如何实现的多agent通信？ task - centric是怎么实现的？ 

为什么这里是空的？

```
Team conversation
How the helpers coordinated — mailbox messages, shared notes, and per-agent runs.

Messages between helpers (0)
No direct mailbox traffic this visit — the helpers coordinated through the shared notes (blackboard) on the right and the agent runs below it. Click any blackboard key to read what they wrote.
```

请您详细给我解释目前的多agent通信到底是如何具体实现的全流程， 请您彻底详细深入的把每一个细节讲清楚，请您多结合流程图讲清楚？



现在我发现一个严重的问题， 由于transcript在医护问诊的时候其实经常会有噪音， 而且会出现一些识别不准的情况， 例如：“Transcript (3 turns)

item_DaMs514bvBx9duIjTCDL1 · completed · ord:high

water

item_DaMs7o6qnSYdJ7vBXIQvz · completed · ord:high

I had a fever and a cough for three days and am allergic to penicillin.

item_DaMsDYFIdstQZkT1ul9QV · completed · ord:high

Yeah, in that case, please take this medicine once a day after meals for three days, and if the fever does not improve after three days, please come back next Friday for a follow-up. And please do a blood test tomorrow morning and bring the report to your next visit.”， 我开始说的doctor就被识别成了water， 导致我的多agent团队合作的时候， 就会受到这个噪音的影响， 例如这是我的团队回答结果
