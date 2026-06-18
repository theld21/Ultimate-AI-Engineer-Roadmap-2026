## 🗺️ PHASE 16 - Reinforcement Learning for AI Engineers

> **Goal:** Understand RL enough to work with RLHF, PPO, and agentic training.

### 16.1 RL Fundamentals

- Markov Decision Processes (MDPs)
- Agent, Environment, State, Action, Reward
- Policy - mapping states to actions
- Value function - expected cumulative reward
- Q-function - value of taking action in state
- Exploration vs exploitation (epsilon-greedy, UCB)
- Discount factor (γ)

### 16.2 Value-Based Methods

- Q-learning
- DQN (Deep Q-Network)
- Double DQN, Dueling DQN, Prioritized Experience Replay

### 16.3 Policy-Based Methods

- REINFORCE (Policy Gradient)
- Actor-Critic methods
- PPO (Proximal Policy Optimization) - used in RLHF
- GRPO (Group Relative Policy Optimization) - used in DeepSeek R1

### 16.4 RL for LLMs (RLHF & Beyond)

- RLHF pipeline: SFT → Reward Model → PPO
- Reward model training on human preferences
- PPO with KL divergence constraint (preventing collapse)
- DPO (Direct Preference Optimization) - simpler RLHF alternative
- RLAIF (RL from AI Feedback) - using LLM as evaluator
- Constitutional AI (Claude's approach)
- Process Reward Models (PRMs) - reward at each reasoning step
- Outcome Reward Models (ORMs) - reward only at final answer

### 16.5 Multi-Agent RL

- Cooperative vs competitive agents
- Game theory basics
- Self-play training
- Multi-agent communication

---

### 📦 Phase 16 Projects

**🟢 Easy: Train a CartPole Agent**
- Implement Q-learning and PPO on CartPole-v1
- Compare convergence, stability
- Stack: gymnasium, stable-baselines3, PyTorch

**🟡 Medium: Reward Model Training**
- Collect preference data (A vs B responses)
- Train a reward model using Bradley-Terry model
- Stack: PyTorch, HuggingFace Transformers, TRL

**🔴 Hard: DPO Fine-tuning Pipeline**
- Collect a preference dataset for a specific task
- Fine-tune a 7B model using DPO
- Evaluate against SFT baseline
- Stack: TRL, HuggingFace PEFT, Axolotl, W&B

---

