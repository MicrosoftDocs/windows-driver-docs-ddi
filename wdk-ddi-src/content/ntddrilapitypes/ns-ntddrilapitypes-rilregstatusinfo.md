---
UID: NS:ntddrilapitypes.RILREGSTATUSINFO
title: RILREGSTATUSINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilregstatusinfo.htm
old-project: netvista
ms.assetid: 12471d22-4d5d-411e-bfde-4d13d7a3bcca
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILREGSTATUSINFO, RILREGSTATUSINFO, RILREGSTATUSINFO structure [Network Drivers Starting with Windows Vista], netvista.rilregstatusinfo, ntddrilapitypes/RILREGSTATUSINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	RILREGSTATUSINFO
product: Windows
targetos: Windows
req.typenames: RILREGSTATUSINFO, *LPRILREGSTATUSINFO
---

# RILREGSTATUSINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILREGSTATUSINFO {
  DWORD                cbSize;
  DWORD                dwParams;
  DWORD                dwExecutor;
  HUICCAPP             hUiccApp;
  RILREGSTAT           dwRegStatus;
  RILACCESSTECHNOLOGY  ratAccessTechnology;
  DWORD                dwSystemCaps;
  DWORD                dwRegRejectReason;
  RILOPERATORNAMES     ronCurrentOperator;
  RILVOICEDOMAIN       dwVoiceDomain;
  RILNETWORKCODE       rncNetworkCode;
} RILREGSTATUSINFO, RILREGSTATUSINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field hUiccApp


### -field dwRegStatus


### -field ratAccessTechnology


### -field dwSystemCaps


### -field dwRegRejectReason


### -field ronCurrentOperator


### -field dwVoiceDomain


### -field rncNetworkCode

