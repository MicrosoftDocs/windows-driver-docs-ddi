---
UID: NS:rilapitypes.RILGETCALLWAITINGSETTINGSPARAMS
title: RILGETCALLWAITINGSETTINGSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallwaitingsettingsparams_2.htm
old-project: netvista
ms.assetid: 87d6c7a0-04ad-4a4e-89c2-7e5d581bd543
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetcallwaitingsettingsparams_2, rilapitypes/RILGETCALLWAITINGSETTINGSPARAMS"
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
-	RILGETCALLWAITINGSETTINGSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETCALLWAITINGSETTINGSPARAMS, *LPRILGETCALLWAITINGSETTINGSPARAMS
req.product: Windows 10 or later.
---

# RILGETCALLWAITINGSETTINGSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETCALLWAITINGSETTINGSPARAMS {
  DWORD  dwExecutor;
  BOOL   fAllClasses;
  DWORD  dwInfoClasses;
} RILGETCALLWAITINGSETTINGSPARAMS, RILGETCALLWAITINGSETTINGSPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field fAllClasses


### -field dwInfoClasses

