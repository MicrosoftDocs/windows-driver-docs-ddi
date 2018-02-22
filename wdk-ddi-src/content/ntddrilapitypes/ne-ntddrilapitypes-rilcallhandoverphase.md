---
UID: NE:ntddrilapitypes.RILCALLHANDOVERPHASE
title: RILCALLHANDOVERPHASE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverphase.htm
old-project: netvista
ms.assetid: c97fcbba-a127-4974-bda7-47456c05558f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RIL_CALLHANDOVERPHASE_FAILED, RIL_CALLHANDOVERPHASE_FAILED, RIL_CALLHANDOVERPHASE_MAX, ntddrilapitypes/RIL_CALLHANDOVERPHASE_COMPLETED, ntddrilapitypes/RILCALLHANDOVERPHASE, netvista.rilcallhandoverphase, RILCALLHANDOVERPHASE, RILCALLHANDOVERPHASE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLHANDOVERPHASE_CANCELLED, ntddrilapitypes/RIL_CALLHANDOVERPHASE_MAX, ntddrilapitypes/RIL_CALLHANDOVERPHASE_CANCELLED, RIL_CALLHANDOVERPHASE_COMPLETED
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILCALLHANDOVERPHASE
product: Windows
targetos: Windows
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




### -field RIL_CALLHANDOVERPHASE_STARTED


### -field RIL_CALLHANDOVERPHASE_COMPLETED


### -field RIL_CALLHANDOVERPHASE_FAILED


### -field RIL_CALLHANDOVERPHASE_CANCELLED


### -field RIL_CALLHANDOVERPHASE_MAX

