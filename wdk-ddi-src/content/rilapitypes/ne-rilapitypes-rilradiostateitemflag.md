---
UID: NE:rilapitypes.RILRADIOSTATEITEMFLAG
title: RILRADIOSTATEITEMFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitemflag_2.htm
old-project: netvista
ms.assetid: 1cf1ebcb-423e-42ee-97aa-bd5f6516e65b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEITEMFLAG, RILRADIOSTATEITEMFLAG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILRADIOSTATEITEMFLAG
req.alt-loc: rilapitypes.h
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
req.typenames: RILRADIOSTATEITEMFLAG
req.product: Windows 10 or later.
---

# RILRADIOSTATEITEMFLAG enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILRADIOSTATEITEMFLAG { 
  RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL,
  RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL,
  RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY,
  RIL_RADIOSTATE_ITEMFLAG_USE_MAX
} RILRADIOSTATEITEMFLAG;
````


## -enum-fields

### -field RIL_RADIOSTATE_ITEMFLAG_USE_UINTVAL


### -field RIL_RADIOSTATE_ITEMFLAG_USE_WSZVAL


### -field RIL_RADIOSTATE_ITEMFLAG_USE_INTARRAY


### -field RIL_RADIOSTATE_ITEMFLAG_USE_UINTARRAY


### -field RIL_RADIOSTATE_ITEMFLAG_USE_BYTEARRAY


### -field RIL_RADIOSTATE_ITEMFLAG_USE_MAX


## -remarks
