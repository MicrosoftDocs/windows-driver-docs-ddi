---
UID: NS:ntddrilapitypes.RILSENDDTMFPARAMS
title: RILSENDDTMFPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsenddtmfparams.htm
old-project: netvista
ms.assetid: b08767f9-6b2d-4930-bd02-ebc89f2bdb7d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSENDDTMFPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILSENDDTMFPARAMS, netvista.rilsenddtmfparams, ntddrilapitypes/RILSENDDTMFPARAMS, RILSENDDTMFPARAMS
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
-	RILSENDDTMFPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSENDDTMFPARAMS, RILSENDDTMFPARAMS"
---

# RILSENDDTMFPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSENDDTMFPARAMS {
  DWORD      dwExecutor;
  char [256] szDTMF;
  DWORD      dwDigitOnTimeMs;
  DWORD      dwDigitOffTimeMs;
} RILSENDDTMFPARAMS, RILSENDDTMFPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field szDTMF


### -field dwDigitOnTimeMs


### -field dwDigitOffTimeMs

