---
UID: NS:rilapitypes.RILRADIOSTATEGROUPS
title: RILRADIOSTATEGROUPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroups_2.htm
old-project: netvista
ms.assetid: 6ef17ba4-2e87-44d6-904c-609030fe9b9b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRADIOSTATEGROUPS, *LPRILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS
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
req.alt-api: RILRADIOSTATEGROUPS
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
req.typenames: *LPRILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS
req.product: Windows 10 or later.
---

# RILRADIOSTATEGROUPS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILRADIOSTATEGROUPS {
  DWORD                  dwCntGroups;
  RILRADIOSTATEGROUP [1] rilGroups;
} RILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS;
````


## -struct-fields

### -field dwCntGroups


### -field rilGroups


## -remarks
