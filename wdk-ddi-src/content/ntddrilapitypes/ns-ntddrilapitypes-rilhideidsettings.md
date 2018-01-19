---
UID: NS:ntddrilapitypes.RILHIDEIDSETTINGS
title: RILHIDEIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideidsettings.htm
old-project: netvista
ms.assetid: 11ca7db9-8e84-4d55-9ea9-7e2ecfa563e0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILHIDEIDSETTINGS, *LPRILHIDEIDSETTINGS, RILHIDEIDSETTINGS
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
req.alt-api: RILHIDEIDSETTINGS
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
req.typenames: *LPRILHIDEIDSETTINGS, RILHIDEIDSETTINGS
---

# RILHIDEIDSETTINGS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILHIDEIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILHIDEIDSETTINGS, RILHIDEIDSETTINGS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwStatus


### -field dwProvisioning


## -remarks
