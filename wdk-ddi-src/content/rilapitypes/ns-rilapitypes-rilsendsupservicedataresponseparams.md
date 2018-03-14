---
UID: NS:rilapitypes.RILSENDSUPSERVICEDATARESPONSEPARAMS
title: RILSENDSUPSERVICEDATARESPONSEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendsupservicedataresponseparams.htm
old-project: netvista
ms.assetid: a339c4fc-87e9-485e-914e-a26e8fac527e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendsupservicedataresponseparams, ntddrilapitypes/RILSENDSUPSERVICEDATARESPONSEPARAMS"
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
-	RILSENDSUPSERVICEDATARESPONSEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDSUPSERVICEDATARESPONSEPARAMS, *LPRILSENDSUPSERVICEDATARESPONSEPARAMS
req.product: Windows 10 or later.
---

# RILSENDSUPSERVICEDATARESPONSEPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSENDSUPSERVICEDATARESPONSEPARAMS {
  DWORD     dwExecutor;
  DWORD     dwDataSize;
  WCHAR [1] wszData;
} RILSENDSUPSERVICEDATARESPONSEPARAMS, RILSENDSUPSERVICEDATARESPONSEPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field dwDataSize


### -field wszData

