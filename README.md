# Kyoko/Sundaymood Studios | Unity Project Architecture Guide

[Skip to Project Architecture](#project-architecture)

**Welcome.**

My name is **Kyo**, also known as **Kyoko** on GitHub, and this repository serves as my **personal and studio-level project architecture guide** for Unity-based development.

This guide documents the **structural standards, conventions, and organizational principles** I follow across my projects—whether they are public repositories, private collaborations, or internal prototypes. Its goal is to help reviewers, collaborators, and future contributors quickly understand how my projects are structured, how systems are grouped, and why certain architectural decisions were made.

- **Note:** This guide is heavily inspired by [Zsfer’s Unity Style Guide](https://github.com/zsfer/unity-style-guide).  
  If you’re looking for deeper or more comprehensive convention details, I highly recommend checking it out.

---

### Background & Intent

I have been programming in **C# and Unity since 2020**, with prior experience in **Unreal Engine 4** before transitioning fully into Unity. While this guide is published and maintained as a formal reference, I consider myself an **intermediate developer**—continually learning, refining, and improving with each project.

This document is not presented as a “perfect” or universal solution. Instead, it reflects a **deliberate, evolving standard** shaped by practical experience, iteration, and long-term maintainability concerns. Think of this repository as my **project and coding bible**:  
a living guide that defines how I structure my work today, and how future projects under **Sundaymood Studios** are expected to follow.

All new projects will adhere to this architecture.  
Older projects may be gradually refactored to align with it where appropriate.

---

## Table of Contents

1. [Introduction](#kyokosundaymood-studios--unity-project-architecture-guide)
2. [Background & Intent](#background--intent)
3. [Project Architecture](#project-architecture)
4. [Code Commandments](#code-commandments)
5. [Script Samples](#script-samples)
6. [Notes & Future Revisions](#notes--future-revisions)

---

## Project Architecture

This section outlines the **standard Unity project structure** used across all Sundaymood Studios projects.  
The architecture follows a **feature-driven, modular approach**, where each gameplay or system feature is treated as a self-contained unit, while shared systems are centralized and reused responsibly.

---
```
[Inside Unity's Explorer Visualized]
-ASSETS-

[Docs] [Features] [Utility] [Art] [Audio] [UI] [Scenes] [Animations] [Shaders] [Fonts] [Plugins] [ThirdParty] [Editor] [Resources] [StreamingAssets] [Addressable] 


Assets/
├─ Docs/ # Documentations and text files.
│ ├─ CHECKLIST.md
│ ├─ Conventions.md
│ └─ FeatureDesign/
│
├─ Features/ # Primary feature modules (self-contained)
│ ├─ FeatureName/
│ │ ├─ Scripts/ # Feature-only runtime code
│ │ ├─ Data/ # ScriptableObject instances
│ │ ├─ Prefabs/ # Feature-specific prefabs
│ │ ├─ Art/ # Feature-specific art assets
│ │ ├─ Audio/ # Feature-specific audio
│ │ ├─ UI/ # Feature-specific UI
│ │ ├─ Editor/ # Feature-specific editor tools
│ │ └─ Tests/ # Feature-level tests
│ │  #Examples of features in actual projects.
│ ├─ Player/
│ ├─ Enemy/
│ ├─ UISystem/
│ ├─ Progression/
│ ├─ Levels/
│ ├─ Scenes/ # Scenes tied to this feature
│ └─ DEBUGS/ <- IMPORTANT: ALL DEBUG COMPONENTS (SCRIPTS, PREFABS, CLASSES, ETC) GO HERE!
│
├─ Utility/ # Cross-feature reusable systems
│ ├─ Core/ # Low-level services and managers
│ │ ├─ Services/
│ │ ├─ Managers/
│ │ ├─ Patterns/
│ │ └─ Extensions/
│ │
│ ├─ Systems/ # Global systems (Localization, Analytics, etc.)
│ ├─ ScriptableObjects/ # Reusable ScriptableObject definitions
│ ├─ Prefabs/ # Generic prefabs used across features
│ └─ UI/ # Shared UI components
│
├─ Art/ # Centralized raw art assets
├─ Audio/ # Global audio assets
├─ UI/ # Global UI screens
├─ Scenes/ # Project-level scenes
│ ├─ Bootstrap.unity
│ ├─ MainMenu.unity
│ └─ Persistent/
│
├─ Animation/
├─ Shaders/
├─ Fonts/
├─ Plugins/
├─ ThirdParty/
├─ Editor/ # Project-wide editor tooling
├─ Resources/ # Extremely limited use
├─ StreamingAssets/
├─ Addressable/
├─ Builds/
├─ Tests/
│ ├─ Editor/
│ └─ Playmode/
└─
```
---
## Developer Preferences

The points below summarize several **personal preferences and habits** I commonly follow when developing projects. 
These are not enforced rules, but practical choices that help me stay consistent, organized, and productive.
They are listed in no particular order and may change as tools, experience, and project needs evolve.


### File Headers
![Header Screenshot Example](https://files.catbox.moe/urjg01.png) 

- I prefer using **file header comments** to clearly describe what a script is responsible for. This helps both myself and other developers quickly understand a file at a glance.  
  A reusable template is provided below and can be placed directly into `MonoBehaviourScriptTemplate.txt`.

```
/* =============================================================================
   Project:        #PROJECTNAME#
   File:           #SCRIPTNAME#.cs
   Author:         [Insert Author Name]
   Studio:         [Studio Name]
   Engine:         Unity [Version]
   Created:        #CREATIONDATE#
    ---------------------------------------------------------------------------
    Description:
    [Briefly describe the responsibility of this component.]
    ---------------------------------------------------------------------------
    Notes:
    ---------------------------------------------------------------------------
    - Part of the [Game Title] project by [Studio].
    - Redistribution should credit the author and studio. ([Author Name])
    
    [Add additional notes here]
   ========================================================================== */
```

### Inspector Headers 
![Unity Header Screenshot Example](https://files.catbox.moe/6a3nft.png) 

I frequently use **Headers** to organize scripts and keep the Inspector clean and easy to navigate.
---
## Code Commandments [WORK IN PROGRESS - NOT FINAL (A LOT OF TERRIBLE STANDARDS]

1. Public, _private, internal.
2. SOLID Principles
3. DRY (Don't Repeat Yourself)
4. KISS (Keep It Simple Stupid)
[LEGACY Code] - Prefix based on features
-  Game - G
  = GManager, GEvents, GTimer
- Vehicle - V
  = VWheel, VTransmission, VEngine
// These are only visible on old projects and may be removed in future code

5. Base on Legacy code from old games (Particulary EA and MC)
6. C++ style Code.


