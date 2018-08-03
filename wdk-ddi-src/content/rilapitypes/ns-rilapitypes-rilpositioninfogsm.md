---
UID: NS:rilapitypes.RILPOSITIONINFOGSM
title: RILPOSITIONINFOGSM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfogsm_2.htm
tech.root: netvista
ms.assetid: 6f98e5c7-41f5-434f-a18b-8615494aa220
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILPOSITIONINFOGSM, RILPOSITIONINFOGSM, RILPOSITIONINFOGSM structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfogsm_2, rilapitypes/RILPOSITIONINFOGSM"
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
-	RILPOSITIONINFOGSM
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOGSM, *LPRILPOSITIONINFOGSM
req.product: Windows 10 or later.
---

# RILPOSITIONINFOGSM structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILPOSITIONINFOGSM {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwTimingAdvance;
  DWORD  dwARFCN;
  DWORD  dwBaseStationID;
  DWORD  dwRxLevel;
} RILPOSITIONINFOGSM, RILPOSITIONINFOGSM;
````


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwLocationAreaCode


### -field dwCellID


### -field dwTimingAdvance


### -field dwARFCN


### -field dwBaseStationID


### -field dwRxLevel

