1. fetch popq instruction twice.
2. first time fetch popq, works like iaddq; second
   time fetch popq2, works like mrmovq
3. load/use condition should be popq2 not popq.

|phase|popq rA|popq2 rA|
|-|-|-|
|works like|iadd $8, %rsp|mrmovq -8(%rsp), rA|
|F|valP = PC|valP = PC + 2|
|D|valB=R[rsp]|valB=R[rsp]|
|E|valE=valB+8|valE=valB-8|
|M||valM=M8[valE]|
|W|R[rsp]=valE|R[rA]=valM|