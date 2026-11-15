# Behaviour Tree System (C# / Unity)

A small behaviour tree framework written in C# for Unity, for building decision-making logic out of reusable nodes. Behaviour trees are commonly used for game AI, robotics and simulation.

## Features

- **Composites:** `Sequence`, `Fallback`, `Parallel`, `ParallelHierarchy`, `Random`, `Invert`, `SubTrees`
- **Ready-made leaf nodes:** `Timer`, `LambdaNode`, `LambdaNodeState`, `DebugNode`, `DebugVariableNode`
- **Three node states:** `RUNNING`, `SUCCESS`, `FAILURE`
- **`Tree` base class** (a `MonoBehaviour`) that evaluates the root node every frame

## Example

```csharp
public class DemoTree : Tree
{
    protected override Node SetupTree() =>
        new Fallback(
            new Sequence(
                new IsTheDoorOpen(),
                new GoThroughTheDoor()
            ),
            new OpenTheDoor()
        );
}
```

If the door is open, the agent walks through it. Otherwise it opens the door first. The full example is in [DemoTree.cs](./BehaviourTreeStructure/DemoTree.cs).

## Documentation

- [What is a behaviour tree?](./BehaviourTreeStructure/WhatIsABehaviourTree.md): how the nodes and states work, with diagrams
- [Class diagram](./BehaviourTreeStructure/ClassDiagram.md)
- [Source code](./BehaviourTreeStructure/Code/)

Originally built as a course project in 2024.
