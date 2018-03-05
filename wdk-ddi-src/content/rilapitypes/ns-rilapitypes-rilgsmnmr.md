---
UID: NS:rilapitypes.RILGSMNMR
title: RILGSMNMR
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgsmnmr_2.htm
old-project: netvista
ms.assetid: 9689a069-1235-4898-9610-3023f6e80dda
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILGSMNMR, RILGSMNMR, RILGSMNMR structure [Network Drivers Starting with Windows Vista], netvista.rilgsmnmr_2, rilapitypes/RILGSMNMR"
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
-	RILGSMNMR
product: Windows
targetos: Windows
req.typenames: RILGSMNMR, *LPRILGSMNMR
req.product: Windows 10 or later.
---

# RILGSMNMR structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGSMNMR {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwARFCN;
  DWORD  dwBaseStationID;
  DWORD  dwRxLevel;
} RILGSMNMR, RILGSMNMR;
````


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwLocationAreaCode


### -field dwCellID


### -field dwARFCN


### -field dwBaseStationID


### -field dwRxLevel

