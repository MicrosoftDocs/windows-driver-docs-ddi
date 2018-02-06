---
UID: NS:ntddrilapitypes.RILRTTDATA
title: RILRTTDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrttdata.htm
old-project: netvista
ms.assetid: 037831c7-d0ef-4cbc-a414-a77010e228a5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILRTTDATA structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILRTTDATA, netvista.rilrttdata, RILRTTDATA, *LPRILRTTDATA
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
-	RILRTTDATA
product: Windows
targetos: Windows
req.typenames: "*LPRILRTTDATA, RILRTTDATA"
---

# RILRTTDATA structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILRTTDATA {
  DWORD       cbSize;
  DWORD       dwID;
  DWORD       dwExecutor;
  WCHAR [127] wszRTTData;
} RILRTTDATA, RILRTTDATA;
````


## -struct-fields




### -field cbSize



### -field dwID



### -field dwExecutor



### -field wszRTTData


