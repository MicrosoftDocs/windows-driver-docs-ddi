---
UID: NS:rilapitypes.RILHIDECONNECTEDIDSETTINGS
title: RILHIDECONNECTEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettings.htm
old-project: netvista
ms.assetid: a0445969-b4b5-43f3-a8dc-a8d61bf44d94
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS, RILHIDECONNECTEDIDSETTINGS structure [Network Drivers Starting with Windows Vista], netvista.rilhideconnectedidsettings, ntddrilapitypes/RILHIDECONNECTEDIDSETTINGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILHIDECONNECTEDIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILHIDECONNECTEDIDSETTINGS, *LPRILHIDECONNECTEDIDSETTINGS
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

