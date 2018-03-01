---
UID: NS:rilapitypes.RILDRVNOTIFICATION
title: RILDRVNOTIFICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildrvnotification_2.htm
old-project: netvista
ms.assetid: 30a05e7f-3761-4f73-8938-fb7a0e3a7f4c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILDRVNOTIFICATION, RILDRVNOTIFICATION, RILDRVNOTIFICATION structure [Network Drivers Starting with Windows Vista], netvista.rildrvnotification_2, rilapitypes/RILDRVNOTIFICATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILDRVNOTIFICATION
product: Windows
targetos: Windows
req.typenames: RILDRVNOTIFICATION, *LPRILDRVNOTIFICATION
req.product: Windows 10 or later.
---

# RILDRVNOTIFICATION structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILDRVNOTIFICATION {
  DWORD    cbSize;
  DWORD    cbSizeNeeded;
  DWORD    dwCode;
  HRESULT  hrCmdID;
  DWORD    dwDataSize;
  BYTE [1] pbData;
} RILDRVNOTIFICATION, RILDRVNOTIFICATION;
````


## -struct-fields




### -field cbSize


### -field cbSizeNeeded


### -field dwCode


### -field hrCmdID


### -field dwDataSize


### -field pbData

