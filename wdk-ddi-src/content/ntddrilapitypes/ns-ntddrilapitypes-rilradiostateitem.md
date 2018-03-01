---
UID: NS:ntddrilapitypes.RILRADIOSTATEITEM
title: RILRADIOSTATEITEM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitem.htm
old-project: netvista
ms.assetid: 152e3b52-44e4-4ed7-bfc3-38d0c65725fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILRADIOSTATEITEM, RILRADIOSTATEITEM, RILRADIOSTATEITEM structure [Network Drivers Starting with Windows Vista], netvista.rilradiostateitem, ntddrilapitypes/RILRADIOSTATEITEM"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILRADIOSTATEITEM
product: Windows
targetos: Windows
req.typenames: RILRADIOSTATEITEM, *LPRILRADIOSTATEITEM
---

# RILRADIOSTATEITEM structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILRADIOSTATEITEM {
  DWORD                  dwItemId;
  RILRADIOSTATEITEMFLAG  dwItemFlag;
  DWORD                  dwItemAttributes;
  NULL                   RILITEMVALUEUNION;
  RILITEMVALUEUNION      itemValueUnion;
  int                    intVal;
  unsigned int           uintVal;
  WCHAR [32]             wszVal;
  int [16]               intArray;
  unsigned int [16]      uintArray;
  BYTE [64]              byteArray;
  WCHAR [32]             wszFriendlyName;
  WCHAR [256]            wszItemValueOptions;
} RILRADIOSTATEITEM, RILRADIOSTATEITEM;
````


## -struct-fields




### -field dwItemId


### -field dwItemFlag


### -field dwItemAttributes


### -field itemValueUnion


### -field RILITEMVALUEUNION


### -field wszFriendlyName


### -field wszItemValueOptions


#### - byteArray


#### - intArray


#### - intVal


#### - uintArray


#### - uintVal


#### - wszVal

