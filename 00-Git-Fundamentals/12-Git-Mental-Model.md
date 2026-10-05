# 🧠 Building the Git Mental Model

*(A synthesis of modules 05 through 11)*

When troubleshooting Git, memorizing commands will fail you. You must visualize the state engine.

### The Master Diagram

```text
       LOCAL MACHINE                                    GITHUB
┌─────────────────────────────────────────┐      ┌─────────────────┐
│                                         │      │                 │
│ [Working Tree]  [Index]    [Repository] │      │  [Repository]   │
│   (Files)       (Queue)      (Vault)    │      │    (origin)     │
│      │             │            │       │      │       │         │
│      ├── git add ─>│            │       │      │       │         │
│      │             ├── commit ─>│       │      │       │         │
│      │             │            ├─── git push ────────>│         │
│      │             │            │       │      │       │         │
│      │             │            │<── git fetch ────────┤         │
│      │<─── git switch / restore ┤       │      │                 │
│                                         │      │                 │
└─────────────────────────────────────────┘      └─────────────────┘