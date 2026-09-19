# Related work

Decklog studies a consumption contract between a durable incident history and short-lived execution agents. Each row below is prior art the project must credit and compare against — this table is curated, not exhaustive, and makes no claim that other relevant work does not exist.

| Work | What it already establishes | Relevance to Decklog | Reference |
| --- | --- | --- | --- |
| The Log is the Agent (arXiv 2605.21997v1) | Event-sourced graph of agent activity with replay, fork, diff and lineage; §9 leaves concurrent/distributed writer ordering unresolved | Closest framing; its unresolved ordering question is one of our open questions | [arXiv HTML](https://arxiv.org/html/2605.21997v1) |
| ActiveGraph | Already implements Views, Frames, frame-aware prompt construction, resume, and snapshot/archive compaction | Much of the "reconstruct a task-relevant view" machinery exists here; a comparison must not ignore it | [README @ 8aedb18](https://github.com/yoheinakajima/activegraph/blob/8aedb1866cf5dce056af97529152ffd6f468a1ed/README.md) |
| Orleans virtual actors | Identity separated from activation — an actor is addressable whether or not it is currently executing | "Agent as addressable identity vs. ephemeral execution" is established prior art | [Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/orleans/overview) |
| Temporal | Centralized logical orchestration that persists and recovers execution state | A fair baseline — the durable centralized design can already persist/recover, so comparisons must not handicap it | [Temporal docs](https://docs.temporal.io/temporal-service/temporal-server) |
| Kafka consumer semantics | Partition positions, committed positions, independent subscribers, replacement consumers | Vocabulary and semantics for N:M consumption; a topic is not automatically a global order or a guarantee of ownership of external effects. Kafka is inspiration and a possible substrate, not a selected dependency | [KafkaConsumer javadoc (4.1)](https://kafka.apache.org/41/javadoc/org/apache/kafka/clients/consumer/KafkaConsumer.html) |
| Kreps, "The Log" | Motivates the shared log as a unifying abstraction for data integration | General motivation for shared-log designs | [LinkedIn Engineering blog](https://www.linkedin.com/blog/engineering/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying) |

## Comparison posture

The planned evaluation varies coordination strategy (durable centralized LLM, rule-driven dispatch, N:M consumer-driven) and execution lifetime independently, holding persistence, tools, model, and task conditions comparable. Prior systems above define the baselines; results do not exist yet. See [research/questions.md](research/questions.md) for the open questions.
