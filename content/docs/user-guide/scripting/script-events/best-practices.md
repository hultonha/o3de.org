---
description: ' Learn best practices for using script events in Open 3D Engine. '
linktitle: Best practices
title: Script events best practices
weight: 400
---

The following are some best practices for using script events.

## Ensure Entities are Activated Before Events are Sent 

Sending events during entity activation can have undesired results. Because the order of activation of entities is not guaranteed, when an event is sent during activation, some entities that need to handle the event might not receive it. In particular, the **On Graph Start** and **On Entity Activated** events are subject to activation order issues.

To ensure that all entities that need to listen for and handle a given script event are ready to receive the event, queue the message on the tick bus. One way to implement this strategy in Script Canvas is to connect the **On Graph Start** node to a **Tick Delay** node. The delay helps to ensure that when a script event message is sent, all entities that could possibly be connected to that script event receive the event.

![Using the Tick Delay node in Script Canvas to ensure that entities are activated before events are sent.](/images/user-guide/script-canvas-script-events-9.png)

## Be Aware of Script Event Asset Versioning 

Because Script Events are user-created assets, problems can occur when an asset that is referenced in existing scripts or Script Canvas graphs changes.

{{< note >}}
Script Canvas provides Script Event version validation. When a Script Event asset is modified, Script Canvas updates the Script Event nodes that reference it. If you open a graph that has a Script Event that has been modified, the graph is marked as modified. To update the Script Event nodes to their latest versions, save the graph.
{{< /note >}}

## Use Script Events Instead of the Gameplay Notification Bus System 

Script events offer the following advantages over the gameplay bus system. Script events:
+ Are data driven.
+ Support more data types.
+ Require less maintenance.
+ Can be used in both Script Canvas and Lua.

For these reasons, script events supersede the gameplay notification bus system and the following `GameplayNotificationBus` related classes:
+ `GameplayNotificationBus`
+ `GameplayNotificationId`
+ `BehaviorGameplayNotificationBusHandler`
+ `GameplayEventHandlerNode` (Legacy)

### Migrating to Script Events 

If your project uses `GameplayNotificationBus`, you can modify it to use script events.

**To migrate from GameplayNotificationBus to script events**

1. Create a new Script Event that performs the event messaging that you require.

1. Identify the Script Canvas graphs or Lua scripts that use `GameplayNotificationBus`.

1. Replace the nodes or code that use `GameplayNotificationBus` with either a Script Event **Send** or a Script Event **Receive**.
