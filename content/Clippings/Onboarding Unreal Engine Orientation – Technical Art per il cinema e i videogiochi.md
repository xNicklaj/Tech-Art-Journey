---
title: "Onboarding: Unreal Engine Orientation – Technical Art per il cinema e i videogiochi"
source: "https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-history"
author:
published:
created: 2026-03-13
description:
tags:
  - "clippings"
---


**Slides:** [Open presentation](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/slides.html)

Important🛠️ In-Class Activity

This session includes a hands-on project setup activity that runs through the end of class and continues at home if needed. You will create and configure a UE5 project from scratch — folder structure, a Blender FBX import, a Fab asset, Nanite, Lumen, auto-exposure, and Git LFS — producing the working foundation that Assignment 1 will build on directly. [Full activity brief →](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-activity)

## The Technical Artist Role

A Technical Artist sits between art and engineering — and fully belongs to neither. The work varies by studio, but the core responsibilities are consistent: shader and material authoring, pipeline automation and custom tooling, performance profiling and optimisation, asset integration across DCCs and engine, and rapid prototyping of features before they move to C++ implementation. TAs solve the problems that neither the art department nor the engineering department owns.

In game development and film production — the backbone disciplines of this course — TAs are essential to shipping work that looks right and runs well. The same skills apply in architecture visualisation, automotive, and broadcast, where Unreal Engine is increasingly used as a production tool. The engine is the same; the outputs differ.

For a concrete picture of what TAs do in an Unreal Engine context, read Epic’s [Jobs in Unreal Engine — Technical Artist](https://www.unrealengine.com/en-US/tech-blog/jobs-in-unreal-engine---technical-artist) article. It outlines the responsibilities, the tools, and the position in a production pipeline. For a production-scale example, the [Slay: Virtual Art Department Pipeline](https://www.unrealengine.com/en-US/blog/new-training-videos-explore-slay-virtual-art-department-pipeline) series by Mold3D Studio and Epic Games shows the TA role in action across a real film production — focus on Video 3 (VAD Production Workflows) and Video 4 (Real-Time Asset Creation) for the most relevant material.

## 🗺️ Where to Start: A Guided Path

If you are working through this material independently, follow this sequence. Each step builds on the previous one — the order matters.

1. **Watch: 30 Years of Unreal Engine Evolution** (~12 min) Before touching the engine, understand where it comes from. This video covers the key turning points from UE1 to UE5 in a visual, fast-paced format. Pay attention to the shifts at UE3 (Kismet, the Blueprint precursor) and UE5 (Nanite and Lumen). ([See Section 3: A Brief History](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-history))
2. **Read: Unity to Unreal Engine Overview** (~20 min) Epic’s official architectural translation for Unity developers. Maps the interface, the Actor paradigm, and the coordinate system differences. Read this before opening Unreal — it will save you from the most common confusion points. ([Unity to Unreal Engine Overview — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/unity-to-unreal-engine-overview))
3. **Watch: UE5 Beginner Tutorial for Blender Users — first hour** (~60 min) Unreal Sensei’s tutorial directly contrasts Blender and UE5 workflows. Start with the first hour: interface mapping (0:03:46), viewport navigation, and basic scene setup. Return to the materials section (0:55:41) and Nanite section (2:34:08) after you have a project running. ([See Section 5: The Actor and Blueprint Paradigm](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-actor-blueprint))
4. **Set up your project** (~30 min) Follow [Section 6: Project Setup](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-project-setup) of this guide. Create a project from the Blank template, establish your folder structure, and initialise Git + Git LFS before importing anything.
5. **Watch: The New FAB Unreal Engine Plugin — William Faucher** (~6 min) Short, practical walkthrough of the Fab plugin. Watch this before your first Megascans import — it covers the plugin setup (0:53), adding assets (2:12), and the ORM texture packing change (4:39) that will break old material setups. ([See Section 8: Content Pipeline](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-content-pipeline))
6. **Configure rendering** (~20 min) Follow [Section 7: Rendering Configuration](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-rendering) of this guide. Neutralise auto-exposure, verify Lumen GI, and enable Nanite on your imported meshes.
7. **Read: Quick Start Guide for Blueprints Visual Scripting** (~30 min) Epic’s hands-on introduction to Blueprints. Follow it after you are comfortable navigating the interface and have a project with at least one imported asset. Focus on understanding execution flow (white pins) and events — not on building complex logic. ([Quick Start Guide — Blueprints Visual Scripting](https://dev.epicgames.com/documentation/en-us/unreal-engine/quick-start-guide-for-blueprints-visual-scripting-in-unreal-engine))

## Unreal Engine: A Brief History

UE5 is not a blank slate — it is the result of five paradigm shifts that each redefined what the engine could do. Understanding these moments explains *why* the engine works the way it does today.

**UE1 (1998)** introduced real-time coloured lighting and an integrated level editor (UnrealEd). The core idea — artists edit the world in real time, not through a compile cycle — was radical at the time and defines UE5 today. **UE2 (2002)** shifted to hardware-accelerated rendering, handing the GPU the work that had been done in software. **UE3 (2006)** introduced Kismet, the first visual scripting system, allowing designers to build gameplay logic without C++. Kismet is the direct ancestor of Blueprints. UE3 also introduced multi-threaded architecture — the engine stopped being single-core. **UE4 (2014)** removed UnrealScript entirely, replacing it with Blueprints and C++ as the only two authoring paths. UE4 also made Physically Based Rendering the default shading model — if you have used Blender’s Principled BSDF, you are already familiar with the physical foundation. **UE5 (2022)** removed two hard constraints that had defined real-time 3D for decades: polygon budgets (via Nanite) and lightmap baking (via Lumen). Both systems depend on temporal accumulation (TSR) to stabilise their output — they are designed to work together.

The current release is **UE5.5**, which this course targets. UE5.5 introduces MegaLights (experimental — hundreds of dynamic shadow-casting lights), Nanite support for skeletal meshes, and Fab as the unified marketplace. UE5.6 and UE5.7 are on the horizon with MegaLights moving to production-ready status, Nanite tessellation and displacement stabilising, and Substrate maturing toward production use. Features marked experimental may change between releases.

![](https://www.youtube.com/watch?v=giohsOnsjPY)

TipKey timestamps

0:43 — UE1 and real-time lighting | 1:35 — UE2 hardware acceleration | 3:47 — UE3 and Kismet | 8:14 — UE4 Blueprints and PBR | 10:30 — UE5 Nanite and Lumen

## Interface Orientation: From Unity and Blender

If you have used Unity, the UE5 interface will look familiar — most panels have direct equivalents. The mapping is intentionally straightforward:

| Hierarchy | **Outliner** | Lists all objects in the current level |
| --- | --- | --- |
| Project Panel | **Content Browser** | Browses and manages all project assets |
| Inspector | **Details Panel** | Displays and edits properties of the selected object |
| Scene View | **Viewport** | 3D view of the scene — where you navigate and place objects |
| Prefab | **Blueprint** (class-level) | Reusable, self-contained asset with logic |
| `GameObject` | **Actor** | Base entity in the scene |

The panel names are different, but the concepts map directly. For a complete visual walkthrough of this mapping, watch Gregorio Piscitelli’s tutorial — it demonstrates each panel side-by-side with Unity equivalents and shows how Blueprint logic bridges the gap from Unity’s C# scripting model.

![](https://www.youtube.com/watch?v=23yB)

Note

The Piscitelli tutorial is hosted on Epic’s community platform, not YouTube. If the embed above does not load, access it directly: [Transitioning from Unity to UE5 — Gregorio Piscitelli / Epic Games](https://dev.epicgames.com/community/learning/tutorials/23yB/transitioning-from-unity-to-unreal-engine-5-a-beginner-s-guide).

### Beyond the panel mapping: three key differences

The interface mapping gets you oriented, but three deeper differences will affect your work immediately.

**Coordinate system.** Unity uses Y-up with 1 unit = 1 metre. Unreal uses **Z-up** with 1 unit = **1 centimetre**. An object moved 1 unit in Unity needs 100 units in Unreal. Imported meshes may appear 100× too small or rotated 90°. Blender is also Z-up, which helps — but the scale difference (1m vs 1cm) still requires attention during FBX export. See [Section 8](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-content-pipeline) for the exact export settings.

**Asset pipeline.** In Unity, dragging an `.fbx` into the Project Panel creates a reference to the source file. In Unreal, import converts everything into internal **`.uasset`** files. Source files are not live-linked — if you change something in Blender, you must re-export and re-import. This is a design decision for binary reproducibility, not a limitation. It also has major implications for version control (see [Section 6](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-project-setup)).

**Scripting model.** Unity uses C# scripts attached as components to a `GameObject`, which is a pure container with no intrinsic behaviour. Unreal uses **Blueprint classes** with inheritance — an Actor is a base class that can be extended, not just a container. The result is a hybrid model: inheritance + composition, rather than composition-only. This is the deepest conceptual difference and directly shapes how Blueprints work. See [Section 5](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-actor-blueprint) for the full explanation.

## The Actor and Blueprint Paradigm

### Actors vs GameObjects

In Unity, a `GameObject` is a pure container — it has no intrinsic behaviour. Everything it does comes from attached `MonoBehaviour` scripts. In Unreal, an **Actor** is a base class that can be extended via Blueprint or C++ inheritance. An Actor can have components (like a Unity `GameObject`), but it can also define behaviour directly in the class itself. This hybrid model — inheritance + composition — is the fundamental architectural difference.

Key Actor subclasses you will encounter:

- **Pawn** — an Actor that can be “possessed” by a Controller (the input-handling system). Think of it as a character slot that a player or AI can occupy.
- **Character** — a Pawn with a built-in `CharacterMovementComponent` for walking, jumping, and falling. A Unity `GameObject` with a `CharacterController` is roughly equivalent to an Unreal Character.
- **StaticMeshActor** — an Actor that holds a static mesh. The most common object in any scene.

The Actor class hierarchy matters because it determines what functionality is available by default. Choosing the right base class when creating a Blueprint saves work — you inherit the systems you need rather than building them from components.

For the full class hierarchy and component model, read [Game Objects in Unreal Engine — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/game-objects-in-unreal-engine).

### Blueprints: not scripts — classes

This is the single most important conceptual point about Blueprints. In Unity, scripts are components you attach to things. In Unreal, a Blueprint **is** the thing — it defines an entire class, with components, logic, and variables packaged together.

A Unity Prefab stores configuration — a pre-configured `GameObject` with its components and settings. A Blueprint stores **behaviour** — it is a class definition that can include event handlers, variables, functions, and component hierarchies. This is why Blueprints sit at the centre of almost every UE5 workflow.

Blueprints are compiled code. They are not a visual convenience layer over C++ — they are a first-class authoring system with their own compilation step. A Blueprint can do anything a C++ class can do, with the trade-off of lower runtime performance for computation-heavy operations.

### Blueprint execution model

Blueprints use a left-to-right execution flow. Two types of connections exist:

- **Execution Pins** (white) — determine the order in which nodes run. Drag from one white pin to another to define “do this, then do that.”
- **Data Pins** (coloured) — carry values between nodes. The colour indicates the type: blue for `Boolean`, green for `Float`, red for `String`, yellow for `Vector`, and so on.

**Events** are the entry points — they trigger when something happens. The two most common:

- `Event BeginPlay` — fires once when the game starts (equivalent to Unity’s `Start()`)
- `Event Tick` — fires every frame (equivalent to Unity’s `Update()`)

**Flow Control** nodes manage branching and looping: `Branch` is `if`, `For Loop` iterates, `Sequence` runs multiple paths in order.

If you have used Blender’s shader node editor, the paradigm will feel familiar — nodes connected by wires, data flowing between them. The key distinction: in Blender’s shader nodes, everything is data flow. In Blueprints, execution flow is explicit and separate from data flow.

### Blueprints as a TA tool

TAs use Blueprints to **prototype features rapidly**. Build a fully working mechanic in Blueprints — test it, iterate on it, get feedback — then hand off to C++ engineers for performance-critical reimplementation. This prototyping workflow is one of the core competences this course develops.

In this course, you will use Blueprints for interactive elements, pipeline tools, and quick experiments. You will not use them to build complete games — that is a different discipline. The framing is always: Blueprints as a TA’s prototyping and tooling system.

For a hands-on first Blueprint, follow the official [Quick Start Guide for Blueprints Visual Scripting — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/quick-start-guide-for-blueprints-visual-scripting-in-unreal-engine). For the full reference, see [Blueprints Visual Scripting in Unreal Engine — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/blueprints-visual-scripting-in-unreal-engine).

The Unreal Sensei tutorial covers Blueprints in the context of Blender-to-UE5 workflow translation. It is embedded below — return to it after you have a project running and are comfortable with the interface.

![](https://www.youtube.com/watch?v=IQCNJ9Lpx-s)

TipKey timestamps for the Unreal Sensei tutorial

0:03:46 — Interface mapping | 0:55:41 — Blender materials to Unreal | 1:12:19 — Blender objects to Unreal | 2:34:08 — Nanite geometry

## Project Setup: Templates, Folders, and Version Control

This section walks through setting up a UE5 project correctly from the start. Follow it step by step during the in-class activity — the decisions made here cannot easily be undone later.

### Step 1: Create a project

Open the **Epic Games Launcher** (the UE5 equivalent of Unity Hub). Install the engine version you need (this course uses UE5.5), then create a new project.

Template choice matters:

- **Blank** — the cleanest starting point. No pre-built gameplay logic, no character, no level content. Use this for technical work where you want full control.
- **Third Person** — pre-configures a Character with movement, a camera, and a basic level. Useful when you need to walk through your scene immediately.

For this course, start with **Blank** unless you specifically need a character to navigate your scene. Other templates (First Person, Top Down, Vehicle) pre-configure specific gameplay systems that add complexity you probably don’t need.

For a practical walkthrough of UE5 project anatomy on disk — where files actually live, what the Config, Content, and Saved folders contain — watch the Smart Poly video (see [Smart Poly, UE5 Set Projects & The Project Folder](https://www.youtube.com/watch?v=UVTzVtxxgE0), key timestamps: 3:15 locating the project on disk, 3:46 folder structure).

### Step 2: Establish folder structure

Set this up **before importing any assets**. The folder structure you choose on day one will follow you through the entire project — restructuring later breaks asset references.

Use **feature-based organisation**: group assets by what they belong to, not by what type they are.

**Feature-based** ✓

```
Content/
  MyProject/
    Characters/
      Hero/
        Meshes/
        Materials/
        Textures/
        Animations/
    Environments/
      Forest/
        Meshes/
        Materials/
        Textures/
```

**Asset-type** ✗

```
Content/
  Meshes/
    HeroBody.uasset
    TreeTrunk.uasset
  Textures/
    HeroSkin.uasset
    BarkDiffuse.uasset
  Materials/
    HeroMat.uasset
    BarkMat.uasset
```

Feature-based organisation keeps related assets together — one character’s meshes, textures, and materials live in the same folder. Asset-type organisation scatters them across the project. At scale, asset-type becomes unmanageable. For a deeper discussion, read the folder structure best practices article (see [Sarah, UE5 Project Folder Structure Best Practices](https://medium.com/@sarah.hyperdense/ue5-project-folder-structure-and-organization-best-practices-b9e487c330a3)).

ImportantThe one rule that has no exception

**All file operations happen inside the Content Browser.** Moving, renaming, or deleting files via Windows Explorer bypasses the Redirector system and permanently breaks asset references. If you need to reorganise files after the fact, do it inside the Content Browser, then right-click the folder → **Fix Up Redirectors in Folder**.

### Step 3: Set up version control

UE5 assets are binary `.uasset` files. They cannot be diffed, they cannot be merged, and standard Git treats them as text — resulting in repository bloat, corruption, and failed merges. **Configure Git LFS before the first commit.** Not after you have already pushed binary files — before.

Git LFS (Large File Storage) tracks large binary files separately from the Git repository. You configure it via a `.gitattributes` file in the project root. Here is a starter configuration for UE5 projects:

```
# UE5 binary assets
*.uasset filter=lfs diff=lfs merge=lfs -text
*.umap filter=lfs diff=lfs merge=lfs -text

# Media files
*.png filter=lfs diff=lfs merge=lfs -text
*.jpg filter=lfs diff=lfs merge=lfs -text
*.bmp filter=lfs diff=lfs merge=lfs -text
*.tga filter=lfs diff=lfs merge=lfs -text
*.exr filter=lfs diff=lfs merge=lfs -text
*.hdr filter=lfs diff=lfs merge=lfs -text

# Audio
*.wav filter=lfs diff=lfs merge=lfs -text
*.ogg filter=lfs diff=lfs merge=lfs -text

# 3D formats
*.fbx filter=lfs diff=lfs merge=lfs -text
*.obj filter=lfs diff=lfs merge=lfs -text

# Video
*.mp4 filter=lfs diff=lfs merge=lfs -text
*.mov filter=lfs diff=lfs merge=lfs -text
```

For a complete walkthrough, follow Rambod’s tutorial (see [Rambod, Setting Up Git and Git LFS for UE5](https://dev.epicgames.com/community/learning/tutorials/Yo1O/setting-up-git-and-git-lfs-for-unreal-engine-5-using-github-desktop)). For background on why standard Git fails with UE5, see the Anchorpoint article (see [Anchorpoint, Git with Unreal Engine 5](https://www.anchorpoint.app/blog/git-with-unreal-engine-5)).

### Step 4: Enable One File Per Actor (OFPA)

By default, an entire UE5 level is saved as a single file. If two people edit the same level, the merge will fail — guaranteed. **One File Per Actor (OFPA)** saves each Actor as a separate `.uasset` file, allowing multiple people to edit the same level simultaneously.

OFPA is enabled by default in new UE5 projects, but verify it: Project Settings → **Use External Actors** → Enabled. Without OFPA, collaborative level editing on Git is effectively impossible.

TipPerforce: the industry standard

In AAA studios, **Perforce (Helix Core)** is the standard version control system for Unreal Engine projects. Where Git LFS tracks large files but still allows concurrent edits (and therefore merge conflicts on binary files), Perforce offers **exclusive file locking** — only one person can check out a binary file at a time. This eliminates merge conflicts entirely for binary assets.

Perforce requires server infrastructure and licensing, which makes it impractical for student groups of 2–3. But if you plan to work in a studio environment after graduation, you will almost certainly encounter it. If you want to experiment, the Epic Games Community has a comprehensive Italian-language tutorial: [Guida Completa a Perforce (P4/Helix Core)](https://dev.epicgames.com/community/learning/tutorials/DBkL/unreal-engine-guida-completa-a-perforce-p4-helix-core) (~1 hour). For a comparison of Git and Perforce in an Unreal context, see the JuegoStudio article (see [JuegoStudio, Making Tools Talk](https://www.juegostudio.com/blog/making-tools-talk-how-to-align-pipelines-across-unity-unreal-git-and-perforce)).

This is not mandatory for the course — Git + Git LFS is what we use. But understanding why Perforce exists and what problem it solves is useful professional context.

## Rendering Configuration

### The interconnected system

Nanite, Lumen, and TSR are not three independent features you toggle on and off. They are an interconnected system designed to work together.

**Nanite** is a virtualized micropolygon geometry system. It streams and scales geometric detail dynamically — the engine decides what to render at what resolution. Manual LOD authoring, which was a hard requirement in Unity and Blender’s EEVEE and every prior version of Unreal, is eliminated for supported meshes. Nanite operates at sub-pixel precision, which means it needs temporal stability to avoid shimmering artifacts.

**Lumen** replaces baked lightmaps with fully dynamic global illumination and reflections. In Unity, you bake lightmaps, wait, and rebake after every change. With Lumen, you move a light and see the GI update in real time. Lumen uses software ray tracing by default (via Signed Distance Fields) or hardware ray tracing on RTX hardware. Like Nanite, Lumen’s output needs temporal accumulation to avoid flickering.

**TSR** (Temporal Super Resolution) provides the temporal stability both systems depend on. It renders at a lower internal resolution and reconstructs to near-native quality, saving GPU budget for Nanite and Lumen. Disabling TSR causes Nanite geometry to shimmer and Lumen lighting to flicker — they are designed to work together.

For the technical details behind each system, read the official documentation: [Nanite Virtualized Geometry — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/nanite-virtualized-geometry-in-unreal-engine) and [Lumen Technical Details — Epic Games](https://dev.epicgames.com/documentation/en-us/unreal-engine/lumen-technical-details-in-unreal-engine).

WarningLumen and mesh construction

Lumen’s software ray tracing path uses Signed Distance Fields, which impose constraints on mesh construction. Modular geometry (separate walls, floors, ceilings) traces correctly; monolithic meshes with internal cavities may produce self-occlusion artifacts. Keep this in mind when building environments — it will become important in Assignment 1.

### Anti-aliasing: choosing the right method

| **TSR** | ~1.1–1.5ms | Near-native, some ghosting | Yes | Default for almost every project |
| --- | --- | --- | --- | --- |
| **DLSS** | Plugin | Superior (NVIDIA RTX only) | Yes | If you have RTX hardware and want the best quality |
| **TAA** | Low | Stable but soft | Yes | Legacy UE4 projects, or if TSR ghosting is unacceptable |
| **SMAA** | Very low | Sharp edges | No | Stylized/cel-shaded work without Lumen |
| **MSAA** | High | Sharp | No — forces Forward Rendering | Never in a standard UE5 project |

**TSR is the correct default.** It provides the temporal stability Nanite and Lumen depend on while saving GPU budget through internal resolution scaling. The trade-off is ghosting on fast-moving or high-contrast geometry — you will notice it when rotating the camera quickly. Motion blur partially masks the ghosting, which is by design.

DLSS (Deep Learning Super Sampling) is superior in quality on NVIDIA RTX hardware but requires a plugin. TAA is the UE4 legacy — it works but produces softer images. SMAA provides no temporal stability — Nanite geometry will shimmer and Lumen lighting will flicker. MSAA forces the entire render pipeline into Forward Rendering, abandoning the deferred pipeline and most UE5 flagship features. Avoid it.

For a practical visual comparison of these methods, watch William Faucher’s rendering guide — the anti-aliasing section starts at 4:58, with a direct comparison at 10:22.

![](https://www.youtube.com/watch?v=fVg5ihB8Wdc)

TipKey timestamps for the William Faucher rendering guide

4:58 — Anti-aliasing methods overview | 7:24 — Motion blur and ghosting | 10:22 — Direct AA comparison

For the full technical details on TSR, read the official documentation (see [Epic Games, Temporal Super Resolution](https://dev.epicgames.com/documentation/en-us/unreal-engine/temporal-super-resolution-in-unreal-engine)). For a broader perspective on AA methods in UE5, see the GroundZer0 article (see [GroundZer0, Understanding Anti-Aliasing in UE5](https://medium.com/@GroundZer0/understanding-anti-aliasing-in-unreal-engine-5-4d993140177f)).

### Three critical settings: do these first

Before you start building anything in a new project, configure these three settings. They prevent the most common sources of confusion for new UE5 users.

**1\. Neutralise auto-exposure.** UE5 defaults to automatic eye-adapting exposure — the scene brightness shifts wildly as the camera moves, making you think your lighting is broken. It is not. Drop a **Post Process Volume** into the scene, enable **Infinite Extent (Unbound)**, then set Exposure → Metering Mode → **Manual**. This gives you stable, predictable lighting during authoring.

**2\. Verify Lumen GI is active.** Go to Project Settings → Rendering → Global Illumination → confirm it is set to **Lumen**. New projects should have this by default, but verify — if it is set to something else, your lighting will behave differently than expected.

**3\. Enable Nanite on imported meshes.** Nanite is not project-wide by default — it must be enabled per-mesh. In the Content Browser, right-click an imported static mesh → **Nanite → Enable**. Without this step, you are not using Nanite on that asset, even if the project supports it.

## Content Pipeline: Fab, Blender, and Import Gotchas

### Fab: the unified marketplace

**Fab** is Epic’s unified marketplace, combining Quixel Megascans, Sketchfab, and the Unreal Engine Marketplace into a single platform. It is natively integrated into the UE5.5 editor — install the Fab plugin, browse assets directly from within Unreal, and import with one click. Thousands of photogrammetry-scanned assets, materials, and environments are available for free.

Watch William Faucher’s Fab plugin walkthrough before your first import. It covers plugin setup (0:53), browsing and adding assets (2:12), and the critical ORM texture packing change (4:39).

![](https://www.youtube.com/watch?v=y29jijP6AKA)

WarningORM vs ARD: the texture packing change

Old Megascans assets (from Quixel Bridge) used **ARD** texture channel packing: Albedo, Roughness, Displacement. New Fab assets use **ORM**: Occlusion, Roughness, Metallic. If you follow older tutorials that set up ARD-based materials, those materials **will break** with new Fab assets — the channels are in the wrong slots. If imported textures look wrong, check the channel packing first. See the Fab transition FAQs for details (see [Fab, Quixel to Fab Transition FAQs](https://support.fab.com/s/article/Fab-Transition-FAQs)).

### Blender to Unreal: FBX export settings

FBX is the standard format for importing individual meshes and animations from Blender into UE5. The Interchange Framework handles more complex asset packages, and USD (experimental) supports full scene transfers — but for most work in this course, FBX is the safe default.

Blender assets are **not live-linked** to Unreal. When you import an FBX, Unreal converts it into an internal `.uasset` file. If you change something in Blender, you must re-export the FBX and re-import it in Unreal. There is no live connection.

**Blender FBX export checklist:**

1. Select the objects you want to export
2. File → Export → FBX
3. In the export dialog:
	- **Scale**: set to **1.0** (Blender’s Z-up matches UE5, but 1 Blender unit = 1 metre, while 1 UE5 unit = 1 centimetre — the FBX exporter handles the conversion at scale 1.0)
		- **Apply Transform**: **enabled** — bakes the object’s transforms into the mesh
		- **Forward**: -Y Forward (default)
		- **Up**: Z Up (default — matches UE5)
4. Import into UE5 via Content Browser → Import

TipScale and axis reference

Blender and UE5 are both Z-up, which avoids rotation issues on import. Unity is Y-up — if you are importing assets that were built for Unity, expect a 90° rotation. The scale difference (1m vs 1cm) is handled by the FBX exporter at scale 1.0, but verify the result in the viewport — objects should appear at the correct size relative to the default mannequin (approximately 180cm tall).

For a comprehensive visual walkthrough of the Blender-to-UE5 pipeline — including viewport navigation, material conversion, and Nanite enablement — watch the Unreal Sensei tutorial embedded in [Section 5](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-actor-blueprint). Key timestamps for the import pipeline: 0:55:41 (materials), 1:12:19 (objects), 2:34:08 (Nanite).

### The normal map gotcha

Blender exports **OpenGL** normal maps (Y+). UE5 expects **DirectX** normal maps (Y-). When the convention is wrong, crevices appear to protrude and bumps appear inverted — the surface looks “inside out.”

**Fix**: after importing a normal map texture in UE5, double-click to open it → expand **Advanced** → enable **Flip Green Channel**. This inverts the Y channel to match DirectX convention.

This is one of the most common issues when importing Blender assets. The fix is simple but not obvious if you don’t know what to look for. If a textured surface looks wrong after import and the material setup is correct, check the normal map convention first.

## Documentation and Learning Resources

### Navigating the Unreal ecosystem

Four entry points cover most of what you will need:

**[dev.epicgames.com/documentation](https://dev.epicgames.com/documentation/en-us/unreal-engine/)** — the official API and system documentation. Start here for any engine feature. The documentation is comprehensive but can be dense — skim the overview and limitations sections first, then dive into the details you need.

**[dev.epicgames.com/community](https://dev.epicgames.com/community/)** — community tutorials, guided learning paths, and example projects. When you need a walkthrough rather than a reference, look here.

**[Fab](https://www.fab.com/)** — asset discovery. Before building something from scratch, check if a free asset exists. Megascans photogrammetry assets are particularly useful for environment work.

**YouTube** — two channels consistently produce practical, well-structured, accurate UE5 content: **William Faucher** (rendering, materials, cinematics) and **Unreal Sensei** (beginner-to-intermediate workflows, Blender integration). Prioritise these over generic search results.

### Finding answers: a pattern

When you need to understand something in Unreal, this three-step pattern works for almost any topic:

1. **Start with the official docs.** Search `dev.epicgames.com/documentation` for the feature name (e.g., “Lumen Technical Details”). Skim the overview and limitations sections.
2. **Check the community.** If you need a guided walkthrough, search `dev.epicgames.com/community` for tutorials on the same topic.
3. **Watch a video.** If you need a visual demonstration, search William Faucher’s or Unreal Sensei’s channel. These are consistently more reliable than generic YouTube results.

Concrete example: “I want to understand how Lumen works.” Step 1: search the official docs for “Lumen Technical Details” — read the overview, note the mesh construction constraints. Step 2: search the community for “Lumen tutorial” — find a guided setup walkthrough. Step 3: watch William Faucher’s rendering guide (timestamp 4:58) for a visual comparison of Lumen with different settings.

### The course notebook: NotebookLM

Each topic in this course has a shared **NotebookLM** notebook loaded with curated, authoritative sources. You can query it like a research assistant — “How does Nanite handle skeletal meshes?” — and get answers grounded in the loaded sources, not the open web.

NotebookLM is bounded and reliable precisely because it is limited to the sources we have loaded. It will not hallucinate answers from the open web — if the answer is not in the loaded sources, it will tell you. This makes it more trustworthy than a general web search for course-specific questions.

But NotebookLM is not just a course utility — it is a **transferable skill**. The process of curating authoritative sources, loading them into a bounded context, and querying with precision is how professionals manage complex technical domains. You are not just using a tool — you are learning how to build one. After this course, you should be able to set up a NotebookLM (or equivalent) for any new technical domain you need to learn: your thesis topic, a new engine, a new framework.

The notebook for each topic is your starting point, not your ceiling. Use it to orient yourself, then follow the sources it cites into the official documentation and tutorials.

Tip📒 Onboarding Notebook — Study Companion

The NotebookLM notebook for this topic is loaded with the curated sources from this guide. Use it as a study companion: ask it to explain a concept, walk through a setup step, or find where something is covered. Answers are grounded in the loaded sources only — citation-dense and reliable.

[Open the Onboarding Notebook](https://notebooklm.google.com/notebook/38fd9b39-f412-4901-ac28-106acdfbda70?authuser=2)

## 🛠️ In-Class Activity

There is no deliverable and no grading. The goal is to hit the real friction points yourself — the ones that cannot be conveyed on a slide — and build the muscle memory of a basic UE5 project setup.

This is not a warm-up exercise. What you produce here is the direct foundation for Assignment 1 — the project you configure today is the one you will build on. Start it seriously.

**Format:** Individual or small groups (2–3). Start during the lecture session and complete at home if needed — this is a single continuous activity, not a class exercise with a separate take-home component. Ask questions, compare notes with neighbours, get stuck and unstuck. This is not an exam — it is a sandbox.

Work through the following steps in order. Do not skip ahead — each step creates the foundation for the next.

**1\. Create a new project** Open the Epic Games Launcher, create a new UE5 project. Choose a template — Blank or Third-Person are both fine. Name it clearly and place it somewhere you can find it on disk.

**2\. Set up your folder structure** Before importing anything, create a top-level namespace folder inside `Content/` and organise it by feature, not asset type. Decide your structure now — restructuring later is costly.

**3\. Tame the viewport** Reorient the navigation to match your background — Blender users should switch to pivot orbit (Alt + LMB). Familiarise yourself with the Outliner, Content Browser, and Details Panel. Place a few primitives and move them around.

**4\. Kill auto-exposure** Drop a Post Process Volume into the level. Set it to Infinite Extent (Unbound). Change the Exposure Metering Mode to Manual. Notice the difference.

**5\. Import two assets** Bring in both of the following:

- A simple mesh exported from Blender as FBX. Check your normal maps on import — flip the green channel if lighting looks inverted.
- A free asset from Fab using the native Fab plugin. Note the ORM texture packing on Megascan materials and how it differs from what you may have set up in Blender.

**6\. Enable Nanite and verify Lumen** Right-click your imported static mesh in the Content Browser and enable Nanite. Open Project Settings and confirm Lumen Global Illumination is active. Place a light source and observe dynamic GI in the viewport.

**7\. Check your anti-aliasing** Open Project Settings → Rendering → Anti-Aliasing. Confirm TSR is active. Try switching to TAA and observe the difference in the viewport. Switch back to TSR when done.

**8\. Set up version control** Initialise a Git repository for the project. Configure Git LFS via a `.gitattributes` file to handle binary `.uasset` files. Make your first commit. This is not optional — every assignment assumes your project is versioned from day one.

### If You Get Stuck

The NotebookLM notebook for this lecture is available in the [Documentation and Learning Resources](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-documentation) section of this guide. It contains all the curated sources from the lecture and can answer follow-up questions, provide step-by-step instructions, and cite exactly where the answer comes from. Using it is optional but encouraged — consider it a first experiment with a research tool you can replicate for your own topics.

You can also consult the earlier sections of this guide, which cover each of these steps in depth.

### What You Should Have at the End

Not a finished scene — a correctly configured project:

- A project with a sensible folder structure
- One FBX asset from Blender with correct normal maps
- One Fab asset with ORM textures placed in the scene
- Nanite enabled, Lumen active, auto-exposure disabled, TSR confirmed
- A versioned Git repository with LFS configured
- A sense of where things live in the UE5 interface

This is the baseline every assignment will build from. Start it here. Finish it before Assignment 1 opens.

## 🔧 Common Errors and Troubleshooting

When something breaks, check here first. Each entry follows the same format: what you see → what went wrong → how to fix it.

### Broken asset references after moving files

**Symptom**: assets show as missing (red text in the Content Browser), objects in the level display as blank or placeholder meshes.

**Cause**: files were moved, renamed, or deleted via Windows Explorer instead of the Content Browser. This bypasses the Redirector system.

**Fix**: if the files still exist, move them back to their original location via the Content Browser. Then right-click the folder → **Fix Up Redirectors in Folder**. If files were deleted outside the editor, you may need to re-import from source.

### Scene brightness shifts wildly when moving the camera

**Symptom**: the entire scene gets brighter or darker as you look around. Lighting appears inconsistent.

**Cause**: auto-exposure is active (default in new projects). The engine is simulating eye adaptation.

**Fix**: drop a Post Process Volume → enable Infinite Extent (Unbound) → Exposure → Metering Mode → Manual. See [Section 7](https://francescostrada.github.io/TA-4-cinema-and-game/topics/01-onboarding/#sec-rendering) for the full setup.

### Imported mesh appears tiny or rotated

**Symptom**: a mesh imported from Blender or Unity appears 100× too small, or is rotated 90°.

**Cause**: scale or axis mismatch. UE5 uses Z-up with 1 unit = 1cm. Blender uses Z-up with 1 unit = 1m. Unity uses Y-up with 1 unit = 1m.

**Fix**: for Blender exports, ensure FBX export scale is set to **1.0** and **Apply Transform** is enabled. For Unity assets, expect a 90° rotation correction on import.

### Normal maps look inverted — crevices protrude

**Symptom**: surface detail appears inverted — grooves stick out, bumps go inward.

**Cause**: Blender exports OpenGL normal maps (Y+); UE5 uses DirectX (Y-).

**Fix**: double-click the normal map texture in UE5 → Advanced → enable **Flip Green Channel**.

### Nanite not working on imported mesh

**Symptom**: mesh does not benefit from Nanite — LOD behaviour is traditional, or Nanite visualisation mode shows the mesh as unsupported.

**Cause**: Nanite must be enabled per-mesh. It is not automatic on import. Also, Nanite does not support morph targets.

**Fix**: Content Browser → right-click the mesh → **Nanite → Enable**. If the mesh uses morph targets, Nanite cannot be used — fall back to traditional LODs.

### Git merge fails on.uasset files

**Symptom**: Git reports a merge conflict on a `.uasset` file. The conflict cannot be resolved in a text editor.

**Cause**: `.uasset` files are binary. Git cannot merge them. Two people edited the same asset simultaneously.

**Fix**: choose one version (theirs or yours) — `git checkout --theirs path/to/file.uasset` or `git checkout --ours path/to/file.uasset`. To prevent this: use **OFPA** for level files, and coordinate with your team on who is editing which assets. For studios, this is why Perforce with exclusive file locking exists.

### Fab materials look wrong — metallic or roughness values are off

**Symptom**: imported Megascans material appears too shiny, too rough, or has incorrect ambient occlusion.

**Cause**: the material setup uses ARD (Albedo, Roughness, Displacement) channel packing, but the new Fab asset uses ORM (Occlusion, Roughness, Metallic).

**Fix**: check the texture’s channel packing. If using a custom material, rewire the channels to match ORM. If using Fab’s auto-generated material, it should be correct — check that you are not applying an old Quixel Bridge material to a new Fab asset.

### Lumen GI is not updating — scene looks flat

**Symptom**: lighting appears flat with no bounce light, even though lights are placed in the scene.

**Cause**: Lumen GI may not be active. Check Project Settings → Rendering → Global Illumination — it should be set to **Lumen**, not Screen Space or None.

**Fix**: set Global Illumination to Lumen. If it is already set to Lumen and the scene still looks flat, check that your meshes are modular (separate walls, floors, ceilings) — monolithic meshes with internal cavities can cause self-occlusion artifacts in Lumen’s software ray tracing path.

## 📚 Resource Reference

All resources cited in this guide, grouped by topic. Use this as a quick-reference index — each entry links to the full resource.

### Technical Artist Role

- [Jobs in Unreal Engine — Technical Artist (Epic Games)](https://www.unrealengine.com/en-US/tech-blog/jobs-in-unreal-engine---technical-artist) — Professional role context, responsibilities, and pipeline position.
- [Slay: Virtual Art Department Pipeline (Mold3D Studio / Epic Games)](https://www.unrealengine.com/en-US/blog/new-training-videos-explore-slay-virtual-art-department-pipeline) — TA role in a real film production. Focus on Videos 3 and 4.

### Engine History

- [30 Years of Unreal Engine Evolution — Game Evolutions (YouTube)](https://www.youtube.com/watch?v=giohsOnsjPY) — ~12 min. Visual history from UE1 to UE5.
- [UE 5.5 Release Notes (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-5-5-release-notes) — MegaLights, Nanite skeletal meshes, Fab integration.

### Interface and Paradigm

- [Unity to Unreal Engine Overview (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/unity-to-unreal-engine-overview) — Definitive architectural translation: panel mapping, Actor paradigm, coordinates.
- [Transitioning from Unity to UE5 — Gregorio Piscitelli (Epic Community)](https://dev.epicgames.com/community/learning/tutorials/23yB/transitioning-from-unity-to-unreal-engine-5-a-beginner-s-guide) — ~40 min. Visual demo of the Unity→UE5 transition with Blueprint bridge.
- [UE5 Beginner Tutorial for Blender Users — Unreal Sensei (YouTube)](https://www.youtube.com/watch?v=IQCNJ9Lpx-s) — ~4.5h. 1-to-1 Blender workflow translation. Key timestamps: 0:03:46 interface, 0:55:41 materials, 1:12:19 objects, 2:34:08 Nanite.
- [Game Objects in Unreal Engine (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/game-objects-in-unreal-engine) — Actor class hierarchy and component model.

### Blueprints

- [Quick Start Guide for Blueprints Visual Scripting (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/quick-start-guide-for-blueprints-visual-scripting-in-unreal-engine) — Hands-on first Blueprint walkthrough.
- [Blueprints Visual Scripting in Unreal Engine (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/blueprints-visual-scripting-in-unreal-engine) — Full Blueprint reference documentation.

### Project Setup and Version Control

- [UE5 Project Folder Structure Best Practices (Medium)](https://medium.com/@sarah.hyperdense/ue5-project-folder-structure-and-organization-best-practices-b9e487c330a3) — Feature-based vs asset-type organisation.
- [Setting Up Git and Git LFS for UE5 — Rambod (Epic Community)](https://dev.epicgames.com/community/learning/tutorials/Yo1O/setting-up-git-and-git-lfs-for-unreal-engine-5-using-github-desktop) — ~20 min. Full Git LFS walkthrough.
- [Git with Unreal Engine 5 (Anchorpoint)](https://www.anchorpoint.app/blog/git-with-unreal-engine-5) — Why standard Git fails on `.uasset` files.
- [UE5 Set Projects & The Project Folder — Smart Poly (YouTube)](https://www.youtube.com/watch?v=UVTzVtxxgE0) — ~15 min. Project anatomy on disk.
- [Guida Completa a Perforce — Epic Community (Italian)](https://dev.epicgames.com/community/learning/tutorials/DBkL/unreal-engine-guida-completa-a-perforce-p4-helix-core) — ~1h. AAA-standard version control with exclusive file locking.
- [Making Tools Talk: Unity, Unreal, Git & Perforce (JuegoStudio)](https://www.juegostudio.com/blog/making-tools-talk-how-to-align-pipelines-across-unity-unreal-git-and-perforce) — Comparison of version control approaches.

### Rendering

- [Nanite Virtualized Geometry (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/nanite-virtualized-geometry-in-unreal-engine) — Supported mesh types, per-mesh enablement.
- [Lumen Technical Details (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/lumen-technical-details-in-unreal-engine) — Mesh construction constraints, software RT path.
- [Temporal Super Resolution (Epic Games)](https://dev.epicgames.com/documentation/en-us/unreal-engine/temporal-super-resolution-in-unreal-engine) — TSR cost/quality trade-offs.
- [The 2025 Guide to Rendering in UE5 — William Faucher (YouTube)](https://www.youtube.com/watch?v=fVg5ihB8Wdc) — ~23 min. Anti-aliasing, ghosting, and render settings.
- [Understanding Anti-Aliasing in UE5 (Medium)](https://medium.com/@GroundZer0/understanding-anti-aliasing-in-unreal-engine-5-4d993140177f) — AA method comparison and compatibility matrix.

### Content Pipeline

- [The New FAB Unreal Engine Plugin — William Faucher (YouTube)](https://www.youtube.com/watch?v=y29jijP6AKA) — ~6 min. Fab plugin setup and ORM packing change.
- [Quixel to Fab Transition FAQs (Fab)](https://support.fab.com/s/article/Fab-Transition-FAQs) — Migration details and texture packing changes.