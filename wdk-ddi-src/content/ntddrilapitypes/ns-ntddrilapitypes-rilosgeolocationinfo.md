---
UID: NS:ntddrilapitypes.RILOSGEOLOCATIONINFO
title: RILOSGEOLOCATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilosgeolocationinfo.htm
old-project: netvista
ms.assetid: 9a56152e-fb38-4470-8834-a0cbdd7b70ec
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILOSGEOLOCATIONINFO, ,, A, C, E, F, G, I, L, N, O, P, R, RILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO structure [Network Drivers Starting with Windows Vista], S, T, netvista.rilosgeolocationinfo, ntddrilapitypes/RILOSGEOLOCATIONINFO"
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
-	ntddrilapitypes.h
apiname:
-	RILOSGEOLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: RILOSGEOLOCATIONINFO, *LPRILOSGEOLOCATIONINFO
---

# RILOSGEOLOCATIONINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILOSGEOLOCATIONINFO {
  DWORD                   cbSize;
  DWORD                   dwParams;
  DWORD                   dwLatitude;
  DWORD                   dwLongitude;
  DWORD                   dwAltitude;
  DWORD                   dwAccuracy;
  RILGEOLOCATIONTYPEMASK  dwLocationInformationMask;
  RILSYSTEMTIME           stTimeStamp;
  WCHAR [76]              wszAddressLine1;
  WCHAR [76]              wszAddressLine2;
  WCHAR [76]              wszCity;
  WCHAR [76]              wszState;
  WCHAR [76]              wszCountry;
  WCHAR [15]              wszPostalCode;
  WCHAR [256]             wszFormattedAddress;
  WCHAR [11]              wszCountryCode;
  WCHAR [11]              wszRegionCode;
} RILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwLatitude


### -field dwLongitude


### -field dwAltitude


### -field dwAccuracy


### -field dwLocationInformationMask


### -field stTimeStamp


### -field wszAddressLine1


### -field wszAddressLine2


### -field wszCity


### -field wszState


### -field wszCountry


### -field wszPostalCode


### -field wszFormattedAddress


### -field wszCountryCode


### -field wszRegionCode

