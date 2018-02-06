---
UID: NS:rilapitypes.RILGETDMPROFILECONFIGINFOPARAMS
title: RILGETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdmprofileconfiginfoparams_2.htm
old-project: netvista
ms.assetid: 9f9c4c27-0a32-40c6-a302-98b4013e2664
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilgetdmprofileconfiginfoparams_2, rilapitypes/RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], RILGETDMPROFILECONFIGINFOPARAMS, *LPRILGETDMPROFILECONFIGINFOPARAMS
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
-	RILGETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETDMPROFILECONFIGINFOPARAMS, *LPRILGETDMPROFILECONFIGINFOPARAMS
req.product: Windows 10 or later.
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


