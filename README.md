# CATArena: Engineering-Level Tournament Evaluation Platform for LLM-Driven Code Agents

Visit the preview version of our arxiv paper [here]([https://github.com/AGI-Eval-Official/CATArena/blob/main/CATArena.pdf](https://arxiv.org/abs/2510.26852)). 

## 🎯 Core Positioning

CATArena is an engineering-level tournament evaluation platform for Large Language Model-driven code agents (LLM-driven code agents), based on an iterative competitive peer learning framework. It includes four types of open, rankable board and card games and their variants: Gomoku, Texas Hold'em, Chess, and Bridge, focusing on systematic evaluation of two core capabilities: strategy coding and learning ability.

## 🚀 Openness and Extensibility

- **No Score Ceiling**: CATArena tasks have no explicit score ceiling, supporting agents to continuously improve through multi-round battle log analysis and strategy iteration, dynamically adapting to the rapid evolution of LLM agent capabilities
- **Strong Extensibility**: The framework has strong extensibility, can introduce new games/variant rules (such as Chess960), and can also extend to new domains, maintaining evaluation effectiveness without relying on expert-level manual annotation
- **Continuous Updates**: More new environments will be added in the future.

## 🎮 Supported Game Environments

### 1. Gomoku
- **Location**: `CATArena/gomokugame/`
- **Features**: 15×15 board, symmetric game, medium difficulty
- **Rules**: Win by connecting five stones, supports standard and variant versions

### 2. Texas Hold'em
- **Location**: `CATArena/holdemgame/`
- **Features**: Multi-player card game, simple difficulty, opening randomness
- **Rules**: Supports classic version (52 cards) and variant version (32 cards)

### 3. Chess
- **Location**: `CATArena/chessgame/`
- **Features**: 8×8 board, symmetric game, difficult difficulty
- **Rules**: Standard chess rules, supports variant rule extensions

### 4. Bridge
- **Location**: `CATArena/bridgegame/`
- **Features**: Four-player card game, medium difficulty, opening randomness
- **Rules**: Standard bridge rules, supports open/closed room direction switching


For each game, we provide two example AI, both of which are the results of Code Agent development (we have erased the specific model names and replaced them with demo1 and demo2).


## 🔧 Technical Architecture

### Evaluation Process
1. **Initial Strategy Development (Round 1)**: Agents autonomously code strategies based on game environment code and sample AI implementations, participating in the first round of competition
2. **Iterative Strategy Optimization (Rounds 2~N)**: Agents obtain all previous round participant code and detailed battle logs, analyze historical data, and optimize their own strategies
3. **Multi-round Cycle**: Through multi-round cycles, evaluate agents' learning and adaptation capabilities

### Competition Format
- **Symmetric Games**: Use full round-robin tournaments to ensure sufficient strategy confrontation
- **Asymmetric Games**: Use grouped multi-agent battles with multi-round averaging to reduce randomness impact
- **Repeated Validation**: All competitions are repeated multiple times, and results are averaged for robust evaluation

## 📈 Evaluation Indicator System

### 1. Strategy Coding Ability
Measures the basic ability of agents to abstract game strategies into algorithms and implement them as executable code. Quantified by the average score obtained in battles with all other agents in the first round.

### 2. Learning Ability
Measures agents' ability to improve their own performance using historical information, including:
- **Global Learning**: Agents' learning and adaptation capabilities in multi-round competitions
- **Targeted Learning**: Agents' ability to achieve performance improvement against opponents
- **Self-improvement**: Models' ability to improve their own strategies during iteration



## 🛠️ Usage Guide

### Quick Start
Each game environment has independent README documentation, including:
- Environment installation and dependency configuration
- AI development guides and sample code
- Battle configuration and running methods
- Result analysis and report generation

### Developing Custom AI
1. Refer to `ChatPrompt.py` in each game directory to get development prompts
2. Use your code agent to generate competing AI
3. Configure battle parameters and start services
4. Participate in multi-round iterative battles

### Evaluation Recommendations
- Recommend generating code multiple times (>=4 times) to compare relative rankings
- Focus on models' relative ranking values rather than absolute scores
- Make full use of historical battle logs for strategy optimization

## 📚 Project Structure

```
CATArena/
├── README.md                   # This document
├── README-CN.md               # Chinese version
├── rawDoc                     # Detailed technical documentation
├── gomokugame/                # Gomoku game environment
├── holdemgame/                # Texas Hold'em game environment  
├── chessgame/                 # Chess game environment
└── bridgegame/                # Bridge game environment
```

Each game environment includes:
- Game server and API interfaces
- AI sample code and development tools
- Battle arena system
- Configuration files and logging system

## 🔮 Future Plans

- More new evaluation environments will be added
- Continuous optimization of evaluation indicators and stability

## 📊 Core Evaluation Conclusions

CATArena can effectively distinguish different types of agent capabilities. Detailed evaluation results can be found in our paper [here]([https://github.com/AGI-Eval-Official/CATArena/blob/main/CATArena.pdf](https://arxiv.org/abs/2510.26852)). 


## Citation
```
@misc{fu2025catarenaevaluationllmagents,
      title={CATArena: Evaluation of LLM Agents through Iterative Tournament Competitions}, 
      author={Lingyue Fu and Xin Ding and Yaoming Zhu and Shao Zhang and Lin Qiu and Weiwen Liu and Weinan Zhang and Xuezhi Cao and Xunliang Cai and Jiaxin Ding and Yong Yu},
      year={2025},
      eprint={2510.26852},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2510.26852}, 
}

```




## 📄 License

This project is licensed under the MIT License, welcoming open source community contributions and usage.

