---
UID: NS:rilapitypes.RILCALLERIDSETTINGS
title: RILCALLERIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalleridsettings_2.htm
old-project: netvista
ms.assetid: 129fcbf9-8162-494a-a571-5c604849d387
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILCALLERIDSETTINGS, RILCALLERIDSETTINGS, RILCALLERIDSETTINGS structure [Network Drivers Starting with Windows Vista], netvista.rilcalleridsettings_2, rilapitypes/RILCALLERIDSETTINGS"
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
-	RILCALLERIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILCALLERIDSETTINGS, *LPRILCALLERIDSETTINGS
req.product: Windows 10 or later.
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

