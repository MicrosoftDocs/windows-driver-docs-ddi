---
UID: NS:ntddrilapitypes.RILCBCDMACONFIGINFO
title: RILCBCDMACONFIGINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbcdmaconfiginfo.htm
old-project: netvista
ms.assetid: 6f8b19ee-a079-4408-8567-39ad832879f2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO structure [Network Drivers Starting with Windows Vista], netvista.rilcbcdmaconfiginfo, ntddrilapitypes/RILCBCDMACONFIGINFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCBCDMACONFIGINFO
product: Windows
targetos: Windows
req.typenames: RILCBCDMACONFIGINFO, *LPRILCBCDMACONFIGINFO
---

# RILCBCDMACONFIGINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCBCDMACONFIGINFO {
  BOOL   fAccept;
  DWORD  dwBroadcastMsgLang;
  DWORD  dwBroadcastServiceCategory;
} RILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO;
````


## -struct-fields




### -field fAccept


### -field dwBroadcastMsgLang


### -field dwBroadcastServiceCategory

