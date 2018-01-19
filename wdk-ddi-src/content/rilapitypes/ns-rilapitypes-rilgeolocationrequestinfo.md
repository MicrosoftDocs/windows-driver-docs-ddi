---
UID: NS:rilapitypes.RILGEOLOCATIONREQUESTINFO
title: RILGEOLOCATIONREQUESTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationrequestinfo_2.htm
old-project: netvista
ms.assetid: c9e2bcb8-cd74-4256-9854-bc898fc8cf74
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGEOLOCATIONREQUESTINFO, *LPRILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO
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
req.alt-api: RILGEOLOCATIONREQUESTINFO
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO
req.product: Windows 10 or later.
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


## -remarks
