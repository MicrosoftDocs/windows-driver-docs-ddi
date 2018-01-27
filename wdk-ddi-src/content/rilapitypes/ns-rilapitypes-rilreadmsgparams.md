---
UID: NS:rilapitypes.RILREADMSGPARAMS
title: RILREADMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilreadmsgparams_2.htm
old-project: netvista
ms.assetid: 2b8ee9c8-3945-4350-84dd-4709f162c381
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILREADMSGPARAMS, RILREADMSGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilreadmsgparams_2, *LPRILREADMSGPARAMS, RILREADMSGPARAMS
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
-	RILREADMSGPARAMS
product: Windows
targetos: Windows
req.typenames: *LPRILREADMSGPARAMS, RILREADMSGPARAMS
req.product: Windows 10 or later.
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


