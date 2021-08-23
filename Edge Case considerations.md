# Edge Case considerations

## Tips

- Use class based approach to avoid running into memory cleanup issues between multiple function calls in same environment
- Avoid globals if execution context is not sandboxed | might reuse old values

## Dynamic Programming (DP)

- Are you using the right dimensional DP/Memo Table?
- What is the base condition/recursion state?

## Binary Trees

- Define/Design method signatures for recursive return values.
- Are you removing/decrementing the inserted/incremented values in base condition?
- How are you handling empty node conditions?
- Should you check if node exists before processing?
    - if (root->left) || if (root->right)
- Keep track of only the current path during DFS | (avoid path sum/product, helps simplify)
    - use map to track other path computations

## Backtracking

- Does repositioning the insert/increment condition simplify the logic/lines of code.
- Are you removing/decrementing the inserted/incremented values in base condition?

