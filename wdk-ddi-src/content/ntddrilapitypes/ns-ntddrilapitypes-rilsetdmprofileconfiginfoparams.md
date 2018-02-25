---
UID: NS:ntddrilapitypes.RILSETDMPROFILECONFIGINFOPARAMS
title: RILSETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetdmprofileconfiginfoparams.htm
old-project: netvista
ms.assetid: d485f00e-5fa6-4a01-83fe-78e59a8d8fcb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSETDMPROFILECONFIGINFOPARAMS, ,, A, C, D, E, F, G, I, L, M, N, O, P, R, RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], S, T, netvista.rilsetdmprofileconfiginfoparams, ntddrilapitypes/RILSETDMPROFILECONFIGINFOPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	RILSETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETDMPROFILECONFIGINFOPARAMS, *LPRILSETDMPROFILECONFIGINFOPARAMS
---

# RILSETDMPROFILECONFIGINFOPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETDMPROFILECONFIGINFOPARAMS {
  DWORD                 dwExecutor;
  RILDMCONFIGINFOITEM   dwConfigItem;
  RILDMCONFIGINFOVALUE  rciValue;
} RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwConfigItem


### -field rciValue

