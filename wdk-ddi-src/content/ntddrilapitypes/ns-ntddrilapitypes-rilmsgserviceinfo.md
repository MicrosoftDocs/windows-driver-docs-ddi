---
UID: NS:ntddrilapitypes.RILMSGSERVICEINFO
title: RILMSGSERVICEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgserviceinfo.htm
old-project: netvista
ms.assetid: 21b1c6ef-b8f3-4230-bc3f-7ac19c6cb2d1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGSERVICEINFO, RILMSGSERVICEINFO, *LPRILMSGSERVICEINFO
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
req.alt-api: RILMSGSERVICEINFO
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILMSGSERVICEINFO, *LPRILMSGSERVICEINFO
---

# RILMSGSERVICEINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMSGSERVICEINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwMsgSupport;
  DWORD  dwStoreUsed;
  DWORD  dwStoreTotal;
} RILMSGSERVICEINFO, RILMSGSERVICEINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwMsgSupport


### -field dwStoreUsed


### -field dwStoreTotal


## -remarks
