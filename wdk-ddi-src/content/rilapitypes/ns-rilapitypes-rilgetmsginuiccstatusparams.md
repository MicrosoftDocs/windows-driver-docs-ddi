---
UID: NS:rilapitypes.RILGETMSGINUICCSTATUSPARAMS
title: RILGETMSGINUICCSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetmsginuiccstatusparams.htm
old-project: netvista
ms.assetid: 8f8ccc6e-ceb5-49df-bf1f-7a804850728a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetmsginuiccstatusparams, ntddrilapitypes/RILGETMSGINUICCSTATUSPARAMS"
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
-	RILGETMSGINUICCSTATUSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETMSGINUICCSTATUSPARAMS, *LPRILGETMSGINUICCSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILGETMSGINUICCSTATUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILGETMSGINUICCSTATUSPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwIndex

