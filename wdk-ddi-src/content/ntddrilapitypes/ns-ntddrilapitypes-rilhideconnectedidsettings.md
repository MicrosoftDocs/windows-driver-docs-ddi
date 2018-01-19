---
UID: NS:ntddrilapitypes.RILHIDECONNECTEDIDSETTINGS
title: RILHIDECONNECTEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettings.htm
old-project: netvista
ms.assetid: a0445969-b4b5-43f3-a8dc-a8d61bf44d94
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILHIDECONNECTEDIDSETTINGS, *LPRILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS
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
req.alt-api: RILHIDECONNECTEDIDSETTINGS
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
req.typenames: *LPRILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS
---

# RILHIDECONNECTEDIDSETTINGS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILHIDECONNECTEDIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwStatus


### -field dwProvisioning


## -remarks
