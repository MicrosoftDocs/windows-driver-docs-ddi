---
UID: NE:ntddrilapitypes.RILCALLHANDOVERPHASE
title: RILCALLHANDOVERPHASE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverphase.htm
old-project: netvista
ms.assetid: c97fcbba-a127-4974-bda7-47456c05558f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLHANDOVERPHASE, RILCALLHANDOVERPHASE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLHANDOVERPHASE
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILCALLHANDOVERPHASE
---

# RILCALLHANDOVERPHASE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILCALLHANDOVERPHASE { 
  RIL_CALLHANDOVERPHASE_COMPLETED,
  RIL_CALLHANDOVERPHASE_FAILED,
  RIL_CALLHANDOVERPHASE_CANCELLED,
  RIL_CALLHANDOVERPHASE_MAX
} RILCALLHANDOVERPHASE;
````


## -enum-fields

### -field RIL_CALLHANDOVERPHASE_COMPLETED


### -field RIL_CALLHANDOVERPHASE_FAILED


### -field RIL_CALLHANDOVERPHASE_CANCELLED


### -field RIL_CALLHANDOVERPHASE_MAX


## -remarks
