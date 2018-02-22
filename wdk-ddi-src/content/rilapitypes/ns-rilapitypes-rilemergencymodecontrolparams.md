---
UID: NS:rilapitypes.RILEMERGENCYMODECONTROLPARAMS
title: RILEMERGENCYMODECONTROLPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencymodecontrolparams_2.htm
old-project: netvista
ms.assetid: 240414c7-c035-462c-8319-d7ac192c712a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilemergencymodecontrolparams_2, rilapitypes/RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILEMERGENCYMODECONTROLPARAMS
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYMODECONTROLPARAMS, *LPRILEMERGENCYMODECONTROLPARAMS
req.product: Windows 10 or later.
---

# RILEMERGENCYMODECONTROLPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILEMERGENCYMODECONTROLPARAMS {
  DWORD                                 dwExecutor;
  RILEMERGENCYMODECONTROLPARAMSCONTROL  dwEmergencyModeControl;
} RILEMERGENCYMODECONTROLPARAMS, RILEMERGENCYMODECONTROLPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwEmergencyModeControl

