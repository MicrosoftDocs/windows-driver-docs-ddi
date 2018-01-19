---
UID: NS:ntddrilapitypes.RILRADIOSTATEITEMS
title: RILRADIOSTATEITEMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostateitems.htm
old-project: netvista
ms.assetid: 26b2521c-7008-437d-aed3-3ed2be5d5959
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEITEMS, *LPRILRADIOSTATEITEMS, RILRADIOSTATEITEMS
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
req.alt-api: RILRADIOSTATEITEMS
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILRADIOSTATEITEMS, RILRADIOSTATEITEMS
---

# RILRADIOSTATEITEMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRADIOSTATEITEMS {
  DWORD                 dwGroupId;
  DWORD                 dwCntItems;
  RILRADIOSTATEITEM [1] rilItems;
} RILRADIOSTATEITEMS, RILRADIOSTATEITEMS;
````


## -struct-fields

### -field dwGroupId


### -field dwCntItems


### -field rilItems


## -remarks
