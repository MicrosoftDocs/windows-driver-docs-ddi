---
UID: NS:rilapitypes.RILRTTDATA
title: RILRTTDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrttdata_2.htm
old-project: netvista
ms.assetid: f481a7e7-ef54-4219-a819-5bb102aecaf6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILRTTDATA, RILRTTDATA, RILRTTDATA structure [Network Drivers Starting with Windows Vista], netvista.rilrttdata_2, rilapitypes/RILRTTDATA"
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
-	RILRTTDATA
product: Windows
targetos: Windows
req.typenames: RILRTTDATA, *LPRILRTTDATA
req.product: Windows 10 or later.
---

# RILRTTDATA structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRTTDATA {
  DWORD                     cbSize;
  DWORD                     dwID;
  DWORD                     dwExecutor;
  WCHAR [MAXLENGTH_RTTDATA] wszRTTData;
} RILRTTDATA, RILRTTDATA;
````


## -struct-fields




### -field cbSize


### -field dwID


### -field dwExecutor


### -field wszRTTData

