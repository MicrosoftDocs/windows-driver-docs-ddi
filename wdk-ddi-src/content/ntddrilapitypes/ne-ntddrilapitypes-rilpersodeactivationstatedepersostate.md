---
UID: NE:ntddrilapitypes.RILPERSODEACTIVATIONSTATEDEPERSOSTATE
title: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstatedepersostate.htm
old-project: netvista
ms.assetid: 81147a47-b5aa-4f00-812d-2c6cf9d5ab8b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_DEPERSOSTATE_PUK_BLOCKED, RILPERSODEACTIVATIONSTATEDEPERSOSTATE, RILPERSODEACTIVATIONSTATEDEPERSOSTATE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_DEPERSOSTATE_MAX, ntddrilapitypes/RIL_DEPERSOSTATE_CK_REQUIRED, ntddrilapitypes/RILPERSODEACTIVATIONSTATEDEPERSOSTATE, RIL_DEPERSOSTATE_MAX, RIL_DEPERSOSTATE_PUK_REQUIRED, ntddrilapitypes/RIL_DEPERSOSTATE_PUK_BLOCKED, RIL_DEPERSOSTATE_CK_REQUIRED, netvista.rilpersodeactivationstatedepersostate, ntddrilapitypes/RIL_DEPERSOSTATE_PUK_REQUIRED
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
-	RILPERSODEACTIVATIONSTATEDEPERSOSTATE
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
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

