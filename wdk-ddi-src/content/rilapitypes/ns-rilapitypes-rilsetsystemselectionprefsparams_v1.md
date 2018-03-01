---
UID: NS:rilapitypes.RILSETSYSTEMSELECTIONPREFSPARAMS_V1
title: RILSETSYSTEMSELECTIONPREFSPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsystemselectionprefsparams_v1.htm
old-project: netvista
ms.assetid: 9b5cbd12-76b1-492e-828e-39a955f6d15c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1 structure [Network Drivers Starting with Windows Vista], netvista.rilsetsystemselectionprefsparams_v1, ntddrilapitypes/RILSETSYSTEMSELECTIONPREFSPARAMS_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILSETSYSTEMSELECTIONPREFSPARAMS_V1
product: Windows
targetos: Windows
req.typenames: RILSETSYSTEMSELECTIONPREFSPARAMS_V1, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V1
req.product: Windows 10 or later.
---

# RILSETSYSTEMSELECTIONPREFSPARAMS_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETSYSTEMSELECTIONPREFSPARAMS_V1 {
  DWORD                       dwFlags;
  RILSYSTEMSELECTIONPREFS_V1  rilSystemSelectionPrefs;
} RILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1;
````


## -struct-fields




### -field dwFlags


### -field rilSystemSelectionPrefs

