# Texas Hold'em Reinforcement Learning Agent

A tabular RL implementation for 2-player Texas Hold'em poker, exploring SARSA, Q-Learning, and Monte Carlo AfterState methods across three experimental phases.

## Repository Structure

| File | Description |
|---|---|
| `group_project_poker_submission_clean.ipynb` | **Phase 1 + Extension 2 (Self-Play)** — Single-hand baseline, all three algorithms, self-play SARSA & Q-Learning, human evaluation demo |
| `group_project_poker_submission_multi.ipynb` | **Extension 1** — 20-hand episode experiments with persistent stack |

## Experimental Phases

### Phase 1 — Single-Hand, Rule-Based Opponent
- **State space**: 1,296 states (9 × 3 × 4 × 4 × 3)
- **Algorithms**: SARSA, Q-Learning, MC AfterState
- **Key result**: MC AfterState +25.60, SARSA +22.01, Q-Learning +1.46 avg reward

### Extension 1 — 20-Hand Episodes
- Each episode: 20 sequential hands, persistent chip stack
- Trained with 1,000 episodes; MC AfterState continues to lead (+365.52)

### Extension 2 — Self-Play
- SP-SARSA agent trained against a frozen copy of itself
- Opponent policy updated every 5,000 episodes, ε-decay 0.30 → 0.01
- SP-SARSA reaches ~165 avg reward vs Phase 1 baseline of ~22

## Dependencies

```bash
pip install pypokerengine treys numpy matplotlib ipywidgets
```

## Usage

Open and run each notebook in order. The interactive demo at the end of `submission_clean.ipynb` allows human play against the trained SP-SARSA agent.

## Results Summary

| Agent | Avg Reward | Win Rate |
|---|---|---|
| Random | −4.23 | 49.3% |
| SARSA | +22.01 | 69.6% |
| Q-Learning | +1.46 | 76.3% |
| MC AfterState | +25.60 | 69.9% |
| SP-SARSA (vs Phase 1) | +213.67 | — |
