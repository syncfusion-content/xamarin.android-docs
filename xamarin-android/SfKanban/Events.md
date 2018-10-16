---
layout: post
title: Events in xamarin.android Kanban control
description: Kanban Events
platform: xamarin.android
control: Kanban
documentation: ug
---

# Events

## ItemTapped

[`ItemTapped`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~ItemTapped_EV.html) event is triggered when you tap any card. The argument contains the following information:

* [`Column`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanTappedEventArgs~Column.html): Gets the column of a card.
* [`Data`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanTappedEventArgs~Data.html): Gets the underlying model of a card.
* [`Index`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanTappedEventArgs~Index.html): Gets the index of a card in a column.
* [`ViewCell`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanTappedEventArgs~ViewCell.html): Gets the tapped view cell.

## DragStart

[`DragStart`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~DragStart_EV.html) event is triggered when you start to drag a card. The argument contains the following information:

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragStartEventArgs~Cancel.html): Cancels the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~Data.html): Gets the underlying model of a card.
* [`KeepItem`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragStartEventArgs~KeepItem.html): Determines whether to keep the dragged card in the source location until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceColumn.html): Gets the source column of a card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceIndex.html): Gets the index of the card in a source column.

## DragEnd  

[`DragEnd`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~DragEnd_EV.html) event is triggered whenever a card is dropped or a dragging action is canceled. The argument contains the following information:

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEndEventArgs~Cancel.html): Cancels the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~Data.html): Gets the underlying model of a card.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceColumn.html): Gets the source column of a card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceIndex.html): Gets the index of the card in a source column.
* [`TargetCategory`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEndEventArgs~TargetCategory.html): Gets the category of a column where the card is going to be dropped.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEndEventArgs~TargetColumn.html): Gets the current column, which is the drop target for a card.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEndEventArgs~TargetIndex.html): Gets the index of the card in a target column.

## DragEnter 

[`DragEnter`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~DragEnter_EV.html) event is triggered when a card enters into a column when dragging. The argument contains the following information:

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs~Cancel.html): Cancels the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~Data.html): Gets the underlying model of a card.
* [`IsAboveMaximumLimit`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs~IsAboveMaximumLimit.html): Determines whether the total cards count of the target column should be above the maximum limit if you drop the card in target column. You can define the maximum limit of the cards using the `KanbanColumn.MaximumLimit` property.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceColumn.html): Gets the source column of a card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceIndex.html): Gets the index of the card in a source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs~TargetColumn.html): Gets the column upon which the card enters.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEnterEventArgs~TargetIndex.html): Gets the index of the card in a target column.

## DragLeave 

[`DragLeave`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~DragLeave_EV.html) event is triggered when a card leaves a column when dragging. The argument contains the following information:

* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~Data.html): Gets the underlying model of a card.
* [`IsBelowMinimumLimit`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragLeaveEventArgs~IsBelowMinimumLimit.html): Determines whether the total cards count of the target column should be below the minimum limit if you remove the card from target column. You can define the minimum limit of the cards using the `KanbanColumn.MinimumLimit` property.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceColumn.html): Gets the source column of a card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceIndex.html): Gets the index of the card in a source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragLeaveEventArgs~TargetColumn.html): Gets the column from which the card leaves.

## DragOver

[`DragOver`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~DragOver_EV.html) event is triggered when a card is dragged to a new index within a column. The argument contains the following information:

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragOverEventArgs~Cancel.html): Cancels the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~Data.html): Gets the underlying model of a card.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceColumn.html): Gets the source column of a card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragEventArgs~SourceIndex.html): Gets the index of the card in source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragOverEventArgs~TargetColumn.html): Gets the current column, which is the drop target for a card.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.KanbanDragOverEventArgs~TargetIndex.html): Gets a new index of a card in target column.

## ColumnsGenerated 

[`ColumnsGenerated`](https://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~ColumnsGenerated_EV.html) event will be fired after the columns are generated automatically. You can access the auto-generated columns using the [`SfKanban.ActualColumns`](http://help.syncfusion.com/cr/cref_files/xamarin-android/Syncfusion.SfKanban.Android~Syncfusion.SfKanban.Android.SfKanban~ActualColumns.html) property.

