---
UID: NS:rilapitypes.RILGEOLOCATIONREQUESTINFO
title: RILGEOLOCATIONREQUESTINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationrequestinfo_2.htm
old-project: netvista
ms.assetid: c9e2bcb8-cd74-4256-9854-bc898fc8cf74
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RILGEOLOCATIONREQUESTINFO, *LPRILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO structure [Network Drivers Starting with Windows Vista], netvista.rilgeolocationrequestinfo_2, RILGEOLOCATIONREQUESTINFO
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
-	RILGEOLOCATIONREQUESTINFO
product: Windows
targetos: Windows
req.typenames: RILGEOLOCATIONREQUESTINFO, *LPRILGEOLOCATIONREQUESTINFO
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

