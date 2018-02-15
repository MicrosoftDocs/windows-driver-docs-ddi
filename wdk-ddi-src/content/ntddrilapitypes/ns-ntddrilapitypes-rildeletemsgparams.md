---
UID: NS:ntddrilapitypes.RILDELETEMSGPARAMS
title: RILDELETEMSGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeletemsgparams.htm
old-project: netvista
ms.assetid: e87104d2-96e4-4840-8609-8a75247a039a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILDELETEMSGPARAMS, ntddrilapitypes/RILDELETEMSGPARAMS, *LPRILDELETEMSGPARAMS, RILDELETEMSGPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rildeletemsgparams
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
-	RILDELETEMSGPARAMS
product: Windows
targetos: Windows
req.typenames: RILDELETEMSGPARAMS, *LPRILDELETEMSGPARAMS
---

# RILDELETEMSGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILDELETEMSGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILDELETEMSGPARAMS, RILDELETEMSGPARAMS;
````


## -struct-fields




### -field hUiccApp


### -field dwIndex

