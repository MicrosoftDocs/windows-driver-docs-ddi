---
UID: NS:ntddrilapitypes.RILREADMSGPARAMS
title: RILREADMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilreadmsgparams.htm
old-project: netvista
ms.assetid: feeabcd2-659f-4a87-abdd-cfbf89589c48
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILREADMSGPARAMS, *LPRILREADMSGPARAMS, RILREADMSGPARAMS, netvista.rilreadmsgparams, RILREADMSGPARAMS structure [Network Drivers Starting with Windows Vista]
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
-	RILREADMSGPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILREADMSGPARAMS, RILREADMSGPARAMS"
---

# RILREADMSGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILREADMSGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILREADMSGPARAMS, RILREADMSGPARAMS;
````


## -struct-fields




### -field hUiccApp



### -field dwIndex


