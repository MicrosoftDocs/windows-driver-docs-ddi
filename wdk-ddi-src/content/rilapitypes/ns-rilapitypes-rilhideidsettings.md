---
UID: NS:rilapitypes.RILHIDEIDSETTINGS
title: RILHIDEIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideidsettings_2.htm
old-project: netvista
ms.assetid: a633bc30-521f-4fdb-a4c0-4f72e619c28a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILHIDEIDSETTINGS, RILHIDEIDSETTINGS, RILHIDEIDSETTINGS structure [Network Drivers Starting with Windows Vista], netvista.rilhideidsettings_2, rilapitypes/RILHIDEIDSETTINGS"
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
-	rilapitypes.h
api_name:
-	RILHIDEIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILHIDEIDSETTINGS, *LPRILHIDEIDSETTINGS
req.product: Windows 10 or later.
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

