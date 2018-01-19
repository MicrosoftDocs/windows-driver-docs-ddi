---
UID: NS:ntddrilapitypes.RILCALLMODIFICATIONINFO
title: RILCALLMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfo.htm
old-project: netvista
ms.assetid: 568603d9-0f96-49f7-a6f8-3c69d889cea7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLMODIFICATIONINFO, *LPRILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO
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
req.alt-api: RILCALLMODIFICATIONINFO
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
req.typenames: *LPRILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO
---

# RILCALLMODIFICATIONINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCALLMODIFICATIONINFO {
  DWORD                                    cbSize;
  DWORD                                    dwParams;
  DWORD                                    dwExecutor;
  DWORD                                    dwID;
  RILCALLMODIFICATIONINFOMODIFICATIONTYPE  dwModificationType;
  RILCALLTYPE                              dwOldCallType;
  RILCALLTYPE                              dwNewCallType;
  RILADDRESS                               raAddress;
  RILALPHAIDENTIFIER                       aiIdentifier;
} RILCALLMODIFICATIONINFO, RILCALLMODIFICATIONINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwID


### -field dwModificationType


### -field dwOldCallType


### -field dwNewCallType


### -field raAddress


### -field aiIdentifier


## -remarks
