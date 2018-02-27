---
UID: NS:rilapitypes.RILDISPLAYINFO
title: RILDISPLAYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfo_2.htm
old-project: netvista
ms.assetid: f24d8122-ea07-477f-9cf9-4767cc0fbf86
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILDISPLAYINFO, RILDISPLAYINFO, RILDISPLAYINFO structure [Network Drivers Starting with Windows Vista], netvista.rildisplayinfo_2, rilapitypes/RILDISPLAYINFO"
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
-	RILDISPLAYINFO
product: Windows
targetos: Windows
req.typenames: RILDISPLAYINFO, *LPRILDISPLAYINFO
req.product: Windows 10 or later.
---

# RILDISPLAYINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILDISPLAYINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  RILDISPLAYINFOTYPE  dwType;
  RILDISPLAYINFOTAG   dwTag;
  DWORD               dwMessageSize;
  BYTE [1]            pbMessage;
} RILDISPLAYINFO, RILDISPLAYINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwType


### -field dwTag


### -field dwMessageSize


### -field pbMessage

