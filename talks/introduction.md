# Challenges

Where we started from

```mermaid
flowchart TD
   subgraph Layer1[Layer 1: Developer]
      Developer[Developer]
   end

   subgraph Layer2[Layer 2: LLM]
      Inference[Inference]
   end

   subgraph Layer3[Layer 3: Codebase]
      Codebase[Codebase]
   end

   Developer --> Inference
   Inference --> Codebase
```

Then here 

```mermaid
flowchart TD
   subgraph Layer1[Layer 1: Developer]
      Developer[Developer]
   end

   subgraph Layer2[Layer 2: Copilot/Claude/Codex]
      Inference[Inference]
   end

   subgraph Layer3[Layer 3: Codebase]
      Codebase[Codebase]
   end



   Developer --> Inference
   Inference --> Codebase
   Inference --> Agents

```

Still some common challenges

- The agent takes too long to close the loop.

   `Add a new column for address` - and it's looping for straight 13 minutes.

![Waiting meme](../images/meme_wait.jpg)

- Makes random `Tool` calls.
![Waiting meme](../images/meme_judge.png)

- The agent says `Done`, it's actually `Not`.
![Waiting meme](../images/meme_notdone.png)

- Amnesia Across Sessions.

![Waiting meme](../images/meme_amnesia.png)


# What is what?

```mermaid
flowchart LR
   subgraph EngineeringHarness[Engineering Harness]
      subgraph Harness["Harness<br/>(Claude, Copilot, etc.)"]
         LLM[LLM]
      end
   end

   Harness --> Agents[Agents]
```

# Building Blocks

- Real world analogy

Each new session is equavalent of onboarding a new engineer. A new eng. takes a week to setup his dev environment, to run the app on his machine.

Mental test - fire up claude/copilot and ask it to run your app. How many of you think it will be successful? if yes, how long will it take?

- The agent should have clear instructions/tools/skills to boot the app end to end and verify changes. 

# Self-improving Feedback Loop

After each session, there should be a feedback loop to capture what could have been done to improve the harness.