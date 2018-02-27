---
UID: NS:ntddrilapitypes.RILGETDMPROFILECONFIGINFOPARAMS
title: RILGETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdmprofileconfiginfoparams.htm
old-project: netvista
ms.assetid: df62bc19-81c7-4d80-88ed-5e8a8438d269
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetdmprofileconfiginfoparams, ntddrilapitypes/RILGETDMPROFILECONFIGINFOPARAMS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILGETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETDMPROFILECONFIGINFOPARAMS, *LPRILGETDMPROFILECONFIGINFOPARAMS
---

# RILGETDMPROFILECONFIGINFOPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILGETDMPROFILECONFIGINFOPARAMS {
  DWORD                dwExecutor;
  RILDMCONFIGINFOITEM  dwConfigItem;
} RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwConfigItem

