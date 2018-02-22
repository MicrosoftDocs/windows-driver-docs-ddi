---
UID: NS:ntddrilapitypes.RILERRORDETAILS
title: RILERRORDETAILS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilerrordetails.htm
old-project: netvista
ms.assetid: 9c9aaece-5c16-40c4-a039-5e32541500f7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILERRORDETAILS structure [Network Drivers Starting with Windows Vista], netvista.rilerrordetails, RILERRORDETAILS, ntddrilapitypes/RILERRORDETAILS, *LPRILERRORDETAILS
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
-	RILERRORDETAILS
product: Windows
targetos: Windows
req.typenames: "*LPRILERRORDETAILS, RILERRORDETAILS"
---

# RILERRORDETAILS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILERRORDETAILS {
  DWORD    cbSize;
  DWORD    dwParams;
  HRESULT  hResult;
  DWORD    dw3gppCause;
} RILERRORDETAILS, RILERRORDETAILS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field hResult


### -field dw3gppCause

