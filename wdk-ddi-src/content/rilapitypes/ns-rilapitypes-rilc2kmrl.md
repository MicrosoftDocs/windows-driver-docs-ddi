---
UID: NS:rilapitypes.RILC2KMRL
title: RILC2KMRL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilc2kmrl_2.htm
old-project: netvista
ms.assetid: a06d81d1-9ecc-41da-b0ad-fa878fac382b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILC2KMRL, RILC2KMRL, RILC2KMRL structure [Network Drivers Starting with Windows Vista], netvista.rilc2kmrl_2, rilapitypes/RILC2KMRL"
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
-	RILC2KMRL
product:
- Windows
targetos: Windows
req.typenames: RILC2KMRL, *LPRILC2KMRL
req.product: Windows 10 or later.
---

# RILC2KMRL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILC2KMRL {
  DWORD  dwParams;
  BOOL   fServing;
  DWORD  dwNID;
  DWORD  dwSID;
  DWORD  dwBaseStationID;
  DWORD  dwBaseLat;
  DWORD  dwBaseLong;
  DWORD  dwRefPN;
  DWORD  dwGPSSeconds;
  DWORD  dwPilotStrength;
} RILC2KMRL, RILC2KMRL;
````


## -struct-fields




### -field dwParams


### -field fServing


### -field dwNID


### -field dwSID


### -field dwBaseStationID


### -field dwBaseLat


### -field dwBaseLong


### -field dwRefPN


### -field dwGPSSeconds


### -field dwPilotStrength

