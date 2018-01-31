---
UID: NE:rilapitypes.RILCALLHANDOVERPHASE
title: RILCALLHANDOVERPHASE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverphase_2.htm
old-project: netvista
ms.assetid: 181363b5-08fa-4a6b-aa91-c9827a82b80e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLHANDOVERPHASE_MAX, RILCALLHANDOVERPHASE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLHANDOVERPHASE_FAILED, rilapitypes/RIL_CALLHANDOVERPHASE_CANCELLED, rilapitypes/RILCALLHANDOVERPHASE, RIL_CALLHANDOVERPHASE_CANCELLED, RILCALLHANDOVERPHASE, rilapitypes/RIL_CALLHANDOVERPHASE_FAILED, rilapitypes/RIL_CALLHANDOVERPHASE_COMPLETED, RIL_CALLHANDOVERPHASE_COMPLETED, netvista.rilcallhandoverphase_2, rilapitypes/RIL_CALLHANDOVERPHASE_MAX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLHANDOVERPHASE
product: Windows
targetos: Windows
req.typenames: RILCALLHANDOVERPHASE
req.product: Windows 10 or later.
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



#### - RIL_CALLHANDOVERPHASE_COMPLETED



#### - RIL_CALLHANDOVERPHASE_FAILED



#### - RIL_CALLHANDOVERPHASE_CANCELLED



#### - RIL_CALLHANDOVERPHASE_MAX


