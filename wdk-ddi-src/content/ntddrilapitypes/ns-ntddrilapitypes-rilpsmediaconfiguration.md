---
UID: NS:ntddrilapitypes.RILPSMEDIACONFIGURATION
title: RILPSMEDIACONFIGURATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediaconfiguration.htm
old-project: netvista
ms.assetid: 579a0943-0577-4dde-82d9-4794537e58f4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILPSMEDIACONFIGURATION, *LPRILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION
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
req.alt-api: RILPSMEDIACONFIGURATION
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
req.typenames: *LPRILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION
---

# RILPSMEDIACONFIGURATION structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILPSMEDIACONFIGURATION {
  RILPSMEDIAPREFERENCE  dwMediaPreference;
  DWORD                 dwServiceType;
} RILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION;
````


## -struct-fields

### -field dwMediaPreference


### -field dwServiceType


## -remarks
