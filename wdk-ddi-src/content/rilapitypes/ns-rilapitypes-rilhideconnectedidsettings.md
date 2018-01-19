---
UID: NS:rilapitypes.RILHIDECONNECTEDIDSETTINGS
title: RILHIDECONNECTEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettings_2.htm
old-project: netvista
ms.assetid: ee5111c6-3353-40a9-9b2b-c3d2a595a528
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILHIDECONNECTEDIDSETTINGS, *LPRILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS
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
req.alt-api: RILHIDECONNECTEDIDSETTINGS
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
req.typenames: *LPRILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS
req.product: Windows 10 or later.
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
