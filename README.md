**Problem Description**

In this puzzle, birds with different number tags sit randomly on a power line. The goal is to rearrange them in correct numerical order with the least number of moves.

* **Initial State:** The initial order of the birds sitting on the power line (e.g., [1, 3, 4, 2, 5]).
* **Goal State:** Arranging the birds in numerical order on the power line (e.g., [1, 2, 3, 4, 5]).
* **Successor States:** Birds can exchange places with only one of their neighbors, moving closer to their goal state.
* **State Space:** The set of all possible orders in which the birds sit on the power line before reaching the goal state.

**Heuristic Function:**
* Implemented a heuristic function based on the distance each bird is away from its goal state position.
* Calculated the heuristic distance using the "goal_idx" function, which returns the position where the bird should ideally be placed based on the goal state.
* The heuristic function calculates the distance using the formula: **heu_dist += (abs(i - goal_idx(state[i])))**.

**Solve Function:**
* Introduced an extra cost in the fringe to prioritize birds with the least cost.
* Implemented a loop inside the solve function to shift the birds based on the cost in the fringe queue.
* The priority value **cost = len(state) + h(state)** determines the order in which birds are moved to their goal state.

**Conclusion**

This approach ensures that the birds are rearranged efficiently and with minimum moves to achieve the goal state.
