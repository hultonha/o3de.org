---
description: ' Nest layout components within other layout components in the Open 3D Engine
  UI Editor. '
title: Nesting Layout Components
---

You can nest layout components within other layout components.

To see an in-game example of a completed canvas with a nested layout, open the level UiFeatures in the project SamplesProject. Press **Ctrl+G** to play the game, and then choose **Components**, **Layout Components**, **Nested Layout**. Press **Esc** to exit the game.

To view that same canvas in the **UI Editor**, navigate to the `\Gems\LyShineExamples\Assets\UI\Canvases\LyShineExamples\Comp\Layout` directory and open the `\NestedLayout.uicanvas`.

The following examples shows one large layout row.

![Hierarchy pane with LayoutRow and children](/images/user-guide/game_ui_editor/ui-editor-components-nesting-row.png)

Within the layout row are four columns.

![LayoutColumns within LayoutRow](/images/user-guide/game_ui_editor/ui-editor-components-nesting-column.png)

Within column A, there are three layout rows. Column B has two layout grids. Column C has three images. Column D has one large image consisting of a color.

![Child elements of the LayoutColumns](/images/user-guide/game_ui_editor/ui-editor-components-nesting-nested.png)

The first image in column C has a layout cell component with a minimum height set at 120. This gives it a larger space than its two siblings below it, which do not have **LayoutCell**l components. Layout column D also has a **LayoutCell** component, with a minimum width of 110, giving it more space than the other three columns, which do not have **LayoutCell** components.

![Child elements with LayoutCells](/images/user-guide/game_ui_editor/ui-editor-components-nesting-cell.png)
