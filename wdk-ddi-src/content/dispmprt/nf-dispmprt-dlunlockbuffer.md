---
UID: NF:dispmprt.DlUnlockBuffer
title: DlUnlockBuffer function
author: windows-driver-content
description: Unlocks physical pages described by the specified memory descriptor list.
tech.root: display
ms.assetid: 7292373a-8c56-438a-a0e1-4b217a359d2b
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: function
ms.keywords: DlUnlockBuffer
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
- DlUnlockBuffer
product: 
- Windows
targetos: Windows

---

# DlUnlockBuffer function


## -description

Unlocks physical pages described by the specified memory descriptor list.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param Mdl

The memory descriptor list.


## -returns

This function returns VOID.

## -remarks

## -see-also