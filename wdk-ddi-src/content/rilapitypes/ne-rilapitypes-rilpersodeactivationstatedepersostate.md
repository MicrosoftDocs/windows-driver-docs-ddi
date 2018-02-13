---
UID: NE:rilapitypes.RILPERSODEACTIVATIONSTATEDEPERSOSTATE
title: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstatedepersostate_2.htm
old-project: netvista
ms.assetid: e01aa9fb-a35e-41d4-994b-8a166372caaf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILPERSODEACTIVATIONSTATEDEPERSOSTATE, RILPERSODEACTIVATIONSTATEDEPERSOSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_DEPERSOSTATE_CK_REQUIRED, RILPERSODEACTIVATIONSTATEDEPERSOSTATE, RIL_DEPERSOSTATE_PUK_BLOCKED, netvista.rilpersodeactivationstatedepersostate_2, rilapitypes/RIL_DEPERSOSTATE_MAX, rilapitypes/RIL_DEPERSOSTATE_CK_REQUIRED, rilapitypes/RIL_DEPERSOSTATE_PUK_BLOCKED, RIL_DEPERSOSTATE_MAX, rilapitypes/RIL_DEPERSOSTATE_PUK_REQUIRED, RIL_DEPERSOSTATE_PUK_REQUIRED
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
-	RILPERSODEACTIVATIONSTATEDEPERSOSTATE
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
req.product: Windows 10 or later.
---

# RILPERSODEACTIVATIONSTATEDEPERSOSTATE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILPERSODEACTIVATIONSTATEDEPERSOSTATE { 
  RIL_DEPERSOSTATE_CK_REQUIRED,
  RIL_DEPERSOSTATE_PUK_REQUIRED,
  RIL_DEPERSOSTATE_PUK_BLOCKED,
  RIL_DEPERSOSTATE_MAX
} RILPERSODEACTIVATIONSTATEDEPERSOSTATE;
````


## -enum-fields




### -field RIL_DEPERSOSTATE_READY


### -field RIL_DEPERSOSTATE_CK_REQUIRED


### -field RIL_DEPERSOSTATE_PUK_REQUIRED


### -field RIL_DEPERSOSTATE_PUK_BLOCKED


### -field RIL_DEPERSOSTATE_MAX

