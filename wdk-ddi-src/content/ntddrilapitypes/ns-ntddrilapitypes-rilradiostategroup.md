---
UID: NS:ntddrilapitypes.RILRADIOSTATEGROUP
title: RILRADIOSTATEGROUP
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroup.htm
old-project: netvista
ms.assetid: e3ad8454-0e23-48fd-a6ef-c9257dc4816d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEGROUP, *LPRILRADIOSTATEGROUP, RILRADIOSTATEGROUP
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
req.alt-api: RILRADIOSTATEGROUP
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
req.typenames: *LPRILRADIOSTATEGROUP, RILRADIOSTATEGROUP
---

# RILRADIOSTATEGROUP structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRADIOSTATEGROUP {
  DWORD      dwGroupId;
  DWORD      dwGroupType;
  DWORD      dwGroupFlags;
  WCHAR [32] wszGroupText;
} RILRADIOSTATEGROUP, RILRADIOSTATEGROUP;
````


## -struct-fields

### -field dwGroupId


### -field dwGroupType


### -field dwGroupFlags


### -field wszGroupText


## -remarks
