# Second Chance - Technical Standards Guide

In this guide, various coding standards for this project are outlined. Please familiarise yourself with them in order to maintain consistency and avoid confusion. For additional information on various aspects of _Second Chance_, please refer to the [design document](https://docs.google.com/document/d/1uJEfSFHQNkcVT3Tw2IoGyKEYMQNpN3YjihiMAOvW4YM/edit?usp=sharing).

## Methodology
As this project is being actively designed and iterated upon during its production, an agile software development approach has been adopted by the programming department.

### Task Allocation (Issues)
_Second Chance_ has a backlog of features that designers will request throughout production. The lead programmer will assign members of the team tasks in order to implement requested features. Tasks will be assigned through the __Issues__ tab in the project’s repository.

All tasks must meet two sets of standards in order to be marked as completed - the _Definition of Done_ and the _Acceptance Criteria_. _Definition of Done_ are a set of standards that apply to all code in the repository, which can be found [below](#definition-of-done). _Acceptance Criteria_ are standards that are unique to the specific task, and are provided in the task.

### Branching Strategy

![branching strategy(1)](https://github.com/user-attachments/assets/9cd5fe1f-1e7e-4bc8-9c38-18092fbd3980)

<sup>Fig. 1 - Branching strategy diagram, proposed by Jaden Lawrence and illustrated by Alexander Schutte</sup>

As of the 5th of November 2024, the repository’s `main` branch can no longer be directly pushed to. Instead, completed features developed by the programming team in their respective feature branches must be pushed to the new `develop` branch, where they will be subjected to QA testing.

### Pull Requests
The `develop` branch will require a pull request in order to be merged to, which will be reviewed by the lead programmer. Pull requests to `develop` will only be accepted if the associated task’s _Acceptance Criteria_ are met, as well as the project’s overall _Definition of Done_ criteria. If any requirements are not met, the pull request will be denied, and the programmer will be asked to make specified changes before creating another pull request.

Once features are merged into the `develop` branch, they will be QA tested by the design team. The design team may at this stage submit a new task in the repository and assign the associated programmer to resolve in their feature branch. Upon finalising a set of features, the lead designer will submit a pull request to the lead developer in order to merge completed and tested features to `main`.

### Definition of Done
For a feature to be considered ready for a pull request, it must meet the following criteria:

- All merge conflicts must be resolved. This can almost always be remedied by pulling `main`, and then merging it into your branch.
- All files must adhere to the naming conventions laid out in the [_Conventions_](#naming-conventions) section.

## Conventions
### Formatting Commits
Commit messages must be formatted correctly and professionally. A commit’s summary should act as a title for the commit, with minimal detail. Its description should be a more detailed explanation of what a developer has done and how to use it. These should also be written to a professional standard with correct grammar and spelling.

See below an example of a well formatted commit message:

_Summary_

Simple AI enemy features.

_Description_

Added a navmesh alongside a new AI controller with a base behaviour tree. Enemies now chase the player until reaching a certain distance away. This will allow them to properly telegraph attacks.

### Blueprints
Blueprints should ideally only be edited by one person at a time. However, this is not always possible. In these cases, a developer should make a copy of the original blueprint, rename it to “[original blueprint name]_[developer name]”, and then continue to work on that version. This will require the developer to connect their new cloned blueprint to any dependent blueprints.

For example, if changes to BP_ThirdPersonCharacter are necessary to complete a task, the default pawn class must be changed within BP_ThirdPersonGameMode to the developer’s new copy.

__If any blueprints have been cloned, they should be listed alongside their dependencies in the description of the relevant pull request.__

Strong communication must be maintained between developers in order to ensure all team members know which blueprints are currently “checked out” by other developers. When a task is complete, blueprints should be organised so that they are straight, compact and commented.

### Naming Conventions

| Subject | Standard |
|---|---|
| Variables | Use Pascal case, e.g. CanTakeDamage |
| Actor class | BP_Actor |
| Actor component | BPC_ActorComponent |
| Blueprint interface | BPI_BlueprintInterface |
| Game instance | GI_Instance |
| Input action | IA_InputAction |
| Widget blueprint | WB_WidgetBlueprint |
| Material | M_Material |
| Particles | P_Particles |
| AI Controller | AI_Character |
| Blackboard | BB_Blackboard |
| Behaviour Tree | BT_Tree |
| Behaviour Tree Task | BTT_Task |
| Behaviour Tree Decorator | BTD_Decorator |
| Environment Query | EQS_QueryName |
| EQS Context | EQSC_Context |

<sup>Fig. 2 - Unreal Engine 5 naming conventions table, proposed by Jaden Lawrence and Nicholas Cornwell, formatted by Alexander Schutte.</sup>
