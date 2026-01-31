Level A: Abstract Core Reasoning (ARC-AGI-2 level, human ~5 min solving time, top models <50%)
Task: You are given a sequence of grid patterns ranging from 3×3 to 9×9 (input → output transformation rules). You must discover the rule zero-shot and generate the output for a test grid.

Example Problem (ASCII text description; real ARC uses colored grids; simplified here):

Input Grid 1:

R R B
R B B
B B B


Output Grid 1:

R R B
R R B
B B B


Input Grid 2:

G Y Y
Y G Y
Y Y G


Output Grid 2:

G Y Y
G G Y
G Y G


Input Grid 3:

O O P P
O O P P
P P W W
P P W W


Output Grid 3:

O O P P
O O P P
O O W W
O O W W


Test Grid (you must generate output):

B G R G
G B G R
R G B G
G R G B


Requirements:

Precisely describe the discovered transformation rule in text (must be concise and executable).

Generate the full output grid for the test input.

If multiple possible rules exist, list them and select the simplest one (Occam's razor).

Level B: PhD-Level Scientific Causal Reasoning (GPQA Diamond level, PhD expert accuracy ~50%)
Problem:
In quantum computing, consider a three-qubit system with initial state:

∣ψ⟩=12(∣000⟩+∣111⟩)
∣ψ⟩=
2
	​

1
	​

(∣000⟩+∣111⟩)

You apply an error: flip the middle qubit (X gate), but then perform simplified surface code error correction (d=3, minimum distance).

Questions:

What is the exact probability that the logical state is recovered after correction?

If the error is a phase flip (Z gate) instead of a bit flip, how would the outcome differ? Why does the surface code behave asymmetrically for these two error types?

Derive why a d=3 code can correct any single-qubit error but may fail with two errors (provide a concrete failure example).

Requirements:

Full derivation (LaTeX-style is allowed).

Pure reasoning only, no external references.

Level C: Real-World Engineering Bug Fix (SWE-bench Verified level, top model pass rate ~30–40%)
Task: Fix a bug in a real open-source library (simplified version of a 2026 popular case).

Pseudo-code with bug (from a PyTorch-like distributed module):

def all_reduce(tensor, group):
    if dist.get_world_size(group) == 1:
        return tensor
    handle = dist.all_reduce(tensor, async_op=True)
    if some_condition:  # actual bug: wrong conditional leads to deadlock
        handle.wait()
    return tensor  # bug: returns original tensor, not the reduced result


Actual Bug Behavior: Occasional deadlocks in multi-process execution + incorrect return value.

Requirements:

Diagnose the root causes (at least two).

Provide a minimal patch in diff format.

Explain why your fix does not introduce regressions (remains backward compatible).# AGI-
