---
UID: NS:rilapitypes.RILERRORDETAILS
title: RILERRORDETAILS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilerrordetails_2.htm
old-project: netvista
ms.assetid: decfcafa-fe8b-44f6-913b-c04cf3b320a3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILERRORDETAILS, netvista.rilerrordetails_2, RILERRORDETAILS, rilapitypes/RILERRORDETAILS, RILERRORDETAILS structure [Network Drivers Starting with Windows Vista]"
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
-	RILERRORDETAILS
product: Windows
targetos: Windows
req.typenames: "*LPRILERRORDETAILS, RILERRORDETAILS"
req.product: Windows 10 or later.
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

