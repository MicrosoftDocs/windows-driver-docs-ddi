---
UID: NF:poscx.PosCxCleanupEvents
title: PosCxCleanupEvents function (poscx.h)
description: PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance.
old-location: pos\poscxcleanupevents.htm
tech.root: pos
ms.assetid: AD97BA14-8786-47A2-B551-2DB6FC7F83A8
ms.date: 02/23/2018
ms.keywords: PosCxCleanupEvents, PosCxCleanupEvents function, pos.poscxcleanupevents, poscx/PosCxCleanupEvents
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- PosCxCleanupEvents
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxCleanupEvents function

## -description

PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param fileObject [in]

A handle to a framework file object for which all pending events should be cleaned up.

## -returns

This function does not return a value.
