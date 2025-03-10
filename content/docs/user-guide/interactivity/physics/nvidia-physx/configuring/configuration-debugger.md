---
description: ' Configure debugging for the PhysX system in Open 3D Engine. '
title: Debugger Configuration
weight: 400
---

In the **PhysX Configuration** tool, you can specify how to interact with the PhysX Visual Debugger (PVD). The PVD is a third-party application that records your PhysX data from O3DE Editor. You can then review this data to see how your physics effects appear.

For more information, see the NVIDIA [PhysX Visual Debugger (PVD)](https://docs.nvidia.com/gameworks/content/gameworkslibrary/physx/guide/Manual/VisualDebugger.html#physxvisualdebugger) documentation.

**To configure the PhysX Visual Debugger**

1. To get started, [download](https://developer.nvidia.com/physx-visual-debugger) the PVD.

    {{< note >}}
You must have a NVIDIA account to download the PVD. If you don't already have an account, follow the steps to create and then sign in your account.
{{< /note >}}

1. Follow the installation steps.

1. After you install the application, open the PVD. This application must be running if you want to record data from O3DE Editor.

1. In O3DE Editor, open a level or create one that has entities with PhysX components. For example, you can create a dynamic entity that falls. For more information, see [Creating a Dynamic PhysX Entity](/docs/user-guide/components/reference/physx/rigid-body-physics#creating-a-dynamic-physx-entity).

1. In O3DE Editor, choose **Tools**, **PhysX Configuration**.

1. Click the **Debugger** tab.

1. You can specify the following settings.

![PhysX Visual Debugger settings.](/images/user-guide/physx/physx-configuration-debugger-1.png)
****


1. To verify that the PVD is connected to O3DE, for **PVD Auto Connect**, choose **Game** or **Editor** and then enter gameplay or editor mode. Depending on what you choose, the following message appears in the console.

   ```
   (PhysX) - Successfully connected to the PhysX Visual Debugger (PVD).
   ```

1. Open the PhysX Visual Debugger to view the recorded information.
**Example**

![Review the recorded data from O3DE Editor in the PhysX Visual Debugger.](/images/user-guide/physx/physx-configuration-debugger-2.png)

1. You can also manually connect or disconnect from the PVD using the following console variable commands.

   ```
   physx_PvdConnect
   ```

   ```
   physx_PvdDisconnect
   ```

   For more information, see [Debugging PhysX](/docs/user-guide/interactivity/physics/debugging/).
