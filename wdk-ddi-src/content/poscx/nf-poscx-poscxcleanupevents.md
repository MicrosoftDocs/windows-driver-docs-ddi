---
UID: NF:poscx.PosCxCleanupEvents
title: PosCxCleanupEvents function (poscx.h)
description: PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance.
old-location: pos\poscxcleanupevents.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosCxCleanupEvents function"]
ms.keywords: PosCxCleanupEvents, PosCxCleanupEvents function, pos.poscxcleanupevents, poscx/PosCxCleanupEvents
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
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxCleanupEvents
 - poscx/PosCxCleanupEvents
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxCleanupEvents
---

# PosCxCleanupEvents function


## -description

PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance.

## -parameters

### -param device 

[in]
A handle to a framework device object that represents the device.

### -param fileObject 

[in]
A handle to a framework file object for which all pending events should be cleaned up.

