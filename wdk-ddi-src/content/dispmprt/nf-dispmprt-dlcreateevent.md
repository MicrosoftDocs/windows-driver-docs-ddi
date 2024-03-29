---
UID: NF:dispmprt.DlCreateEvent
title: DlCreateEvent function
description: Creates an event object.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlCreateEvent function"]
ms.keywords: DlCreateEvent
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlCreateEvent
 - dispmprt/DlCreateEvent
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlCreateEvent
dev_langs:
 - c++
---

# DlCreateEvent function


## -description

Creates an event object.

## -parameters

### -param DeviceHandle

A handle to the device.

### -param EventFlag

Specifies the event type and initial event state.

### -param Unused

Is currently ignored.

### -param ppEvent

Pointer to the memory location at which a pointer to the event object will be returned.

## -returns

This function returns VP_STATUS.

## -remarks

## -see-also

