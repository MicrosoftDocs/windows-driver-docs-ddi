---
UID: NS:rilapitypes.RILSETDMPROFILECONFIGINFOPARAMS
title: RILSETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetdmprofileconfiginfoparams_2.htm
old-project: netvista
ms.assetid: 99513338-a908-4ff7-8fd6-f4224fbdc04f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILSETDMPROFILECONFIGINFOPARAMS, rilapitypes/RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS structure [Network Drivers Starting with Windows Vista], RILSETDMPROFILECONFIGINFOPARAMS, netvista.rilsetdmprofileconfiginfoparams_2"
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
-	RILSETDMPROFILECONFIGINFOPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS"
req.product: Windows 10 or later.
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

