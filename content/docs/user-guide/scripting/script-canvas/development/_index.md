---
description: Create a custom node that you can use in O3DE's Script Canvas.
title: Creating Custom Nodes in Script Canvas
---

Script Canvas uses the [behavior context](behavior-context/). The preferred way to expose functionality in Script Canvas is through behavior context bindings. Behavior context bindings make functionality available to any scripting solution (such as Lua) that also uses the behavior context. However, if you want to create Script Canvas-specific functionality or customized visual scripting experiences, you can use the Script Canvas custom node API.

If your gem provides custom Script Canvas nodes, you must specify a dependency on the Script Canvas Gem. Functionality that you reflect through the behavior context requires no dependency on the Script Canvas Gem.

Custom nodes in Script Canvas take advantage of [Automating boilerplate with AZ Code Generator](/docs/user-guide/engine/autogen) and boilerplate code. This reduces complexity and lets you focus on implementing the behavior of the node.

The following diagram shows the AZ Code Generator process for Script Canvas.

![AZ Code Generator and Script Canvas](/images/user-guide/scripting/script-canvas/script-canvas-custom-nodes-1.png)

In **Step 1**, AZ Code Generator processes `MyNode.h` and looks for code generation tags \(source code location: `dev\Gems\ScriptCanvas\Code\Include\ScriptCanvas\CodeGen\CodeGen.h`\). After processing, AZ Code Generator creates a file called `MyNode.generated.h`.

{{< note >}}
You must include `MyNode.generated.h` in the `MyNode.h` file so that the preprocessor macro that AZ Code Generator produces is resolved by C++ during Step 3.
{{< /note >}}

In **Step 2**, AZ Code Generator processes `MyNode.h` again, but this time produces a `.cpp` file.

{{< note >}}
You must include `MyNode.generated.cpp` the in `MyNode.cpp` file. This ensures that the generated code can be compiled and has access to all the same `#include` declarations as those found in `MyNode.cpp`.
{{< /note >}}

In **Step 3**, AZ Code Generator is finished and the build process continues as normal. `MyNode.cpp` is compiled and succeeds provided all the generated files are correct.

**Topics**
+ [Script Canvas Tags for AZ Code Generator](tags/)
+ [Dynamic Data Slots](custom-nodes-dynamic-data/)
+ [Node Libraries](node-libraries/)
