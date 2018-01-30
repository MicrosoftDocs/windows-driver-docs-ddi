---
UID: NS:rilapitypes.RILDIALEDIDSETTINGS
title: RILDIALEDIDSETTINGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialedidsettings_2.htm
old-project: netvista
ms.assetid: 6c65644b-f3a4-4c7d-91ce-c4b2b1e611e7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rildialedidsettings_2, rilapitypes/RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS structure [Network Drivers Starting with Windows Vista], *LPRILDIALEDIDSETTINGS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILDIALEDIDSETTINGS
product: Windows
targetos: Windows
req.typenames: RILDIALEDIDSETTINGS, *LPRILDIALEDIDSETTINGS
req.product: Windows 10 or later.
---

# RILDIALEDIDSETTINGS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILDIALEDIDSETTINGS {
  DWORD                         cbSize;
  DWORD                         dwParams;
  DWORD                         dwExecutor;
  RILSERVICESETTINGSSTATUS      dwStatus;
  RILSERVICEPROVISIONINGSTATUS  dwProvisioning;
} RILDIALEDIDSETTINGS, RILDIALEDIDSETTINGS;
````


## -struct-fields




### -field cbSize



### -field dwParams



### -field dwExecutor



### -field dwStatus



### -field dwProvisioning


