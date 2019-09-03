---
UID: NF:dispmprt.DlSetEvent
title: DlSetEvent function
author: windows-driver-content
description: Sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.
tech.root: display
ms.assetid: 7c8103ff-2ba6-43be-b9eb-595e510cad84
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
f1_keywords:
 - "dispmprt/DlSetEvent"
ms.keywords: DlSetEvent
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- Displib.lib
- Displib.dll
api_name: 
- DlSetEvent
product: 
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DlSetEvent function


## -description

Sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param pEvent

A pointer to an event.


## -returns

This function returns LONG.

## -remarks

## -see-also
