---
UID: NS:rilapitypes.RILCALLHANDOVERSTATE
title: RILCALLHANDOVERSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverstate_2.htm
old-project: netvista
ms.assetid: 21558cd6-f200-4867-920f-8aaadc9839f8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallhandoverstate_2, rilapitypes/RILCALLHANDOVERSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILCALLHANDOVERSTATE
product: Windows
targetos: Windows
req.typenames: RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE
req.product: Windows 10 or later.
---

# RILCALLHANDOVERSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLHANDOVERSTATE {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RILCALLHANDOVERPHASE  dwPhase;
  RILCALLTYPE           dwOldType;
  RILCALLTYPE           dwNewType;
  DWORD                 dw3gppCause;
} RILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwPhase


### -field dwOldType


### -field dwNewType


### -field dw3gppCause

