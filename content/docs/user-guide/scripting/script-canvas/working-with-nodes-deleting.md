---
description: ' Learn how to delete Script Canvas nodes in Open 3D Engine. '
title: Deleting Nodes
---

Script Canvas offers a variety of techniques for deleting nodes.

**To delete one or more nodes and their connections**

1. Select the node or nodes that you want to delete.

1. Perform one of the following steps.
   + Press **Delete**.
   + Right-click, and then choose **Delete**.

**To delete a single node**
+ On the node that you want to delete, press **Alt+Left-click**. If the deleted node was connected to one other node, the connection is deleted. If the deleted node was connected to two other nodes, the remaining nodes connect to each other.

    ![Using Alt+Left-click to delete a node in Script Canvas editor.](/images/user-guide/scripting/script-canvas/script-canvas-working-with-nodes-24.gif)

    {{< note >}}
You cannot use **Alt+Left-click** to delete more than one node at a time.
{{< /note >}}

**To remove all unused nodes in a graph**
+ In Script Canvas editor, choose **Edit**, **Remove Unused**, **Nodes**.

![Removing all unused nodes from a graph in the Script Canvas editor.](/images/user-guide/scripting/script-canvas/script-canvas-working-with-nodes-25.png)
