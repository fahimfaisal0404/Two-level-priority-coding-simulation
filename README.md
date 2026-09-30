# Two-level-priority-coding-simulation
I studied Dogan et al.’s paper on two-level priority coding. I considered three paths with random blockages, where important data \(U1\) must survive with one path, while less important \(U2\) needs two paths. I compared priority coding with conventional coding.

In Brief: 
I made this to understand the paper "Two-Level Priority Coding for Resilience to Arbitrary Blockage Patterns" (Dogan et al.)

Idea:
- we have 3 paths between source and destination
- some paths can get blocked randomly
- we have 2 types of data: U1 (important) and U2 (less important)
- U1 should be received if at least 1 path is ok
- U2 should be received if at least 2 paths are ok

Groups (from the paper):
 G1 = only 1 path is ok   -> 100, 010, 001  (we need U1)
 G2 = 2 or 3 paths are ok -> 110, 101, 011, 111  (we need U1 and U2)

Scheme A = priority coding (like the paper)
- U1 is sent on all 3 paths (repetition, (3,1) code)
- U2 uses a (3,2) code: send a, b and a XOR b
- each path carries 2 symbols so C = 2, R1 = 1, R2 = 2
- check: R1 + R2/2 = 1 + 1 = 2 = C   (this is equation 6 in the paper)

Scheme B = normal way, no priority
- put everything together and use one (3,2) code
- need 2 paths to get anything

At the end we compare both schemes.
