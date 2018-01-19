---
UID: NS:ntddrilapitypes.RILCALLERIDSETTINGS
title: RILCALLERIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalleridsettings.htm
old-project: netvista
ms.assetid: 3ba2cd72-4678-4ada-9777-12cbb6032628
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLERIDSETTINGS, RILCALLERIDSETTINGS, *LPRILCALLERIDSETTINGS
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
req.alt-api: RILCALLERIDSETTINGS
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
req.typenames: RILCALLERIDSETTINGS, *LPRILCALLERIDSETTINGS
---

# RILCALLERIDSETTINGS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCALLERIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILCALLERIDSETTINGS, RILCALLERIDSETTINGS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwStatus


### -field dwProvisioning


## -remarks
