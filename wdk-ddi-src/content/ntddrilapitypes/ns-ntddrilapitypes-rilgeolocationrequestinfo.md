---
UID: NS:ntddrilapitypes.RILGEOLOCATIONREQUESTINFO
title: RILGEOLOCATIONREQUESTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationrequestinfo.htm
old-project: netvista
ms.assetid: f3fa5212-66c1-45f8-a96f-78d1f2f01fe8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO structure [Network Drivers Starting with Windows Vista], netvista.rilgeolocationrequestinfo, ntddrilapitypes/RILGEOLOCATIONREQUESTINFO"
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
-	RILGEOLOCATIONREQUESTINFO
product: Windows
targetos: Windows
req.typenames: RILGEOLOCATIONREQUESTINFO, *LPRILGEOLOCATIONREQUESTINFO
---

# RILGEOLOCATIONREQUESTINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILGEOLOCATIONREQUESTINFO {
  DWORD  cbSize;
  DWORD  dwLatitude;
  DWORD  dwLongitude;
  DWORD  dwAltitude;
} RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO;
````


## -struct-fields




### -field cbSize


### -field dwLatitude


### -field dwLongitude


### -field dwAltitude

