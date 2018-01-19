---
UID: NS:rilapitypes.RILOPENUICCLOGICALCHANNELINFO
title: RILOPENUICCLOGICALCHANNELINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelinfo_2.htm
old-project: netvista
ms.assetid: f731c790-4348-4c18-aef1-184c3d4bf258
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILOPENUICCLOGICALCHANNELINFO, *LPRILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO
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
req.alt-api: RILOPENUICCLOGICALCHANNELINFO
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
req.typenames: *LPRILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO
req.product: Windows 10 or later.
---

# RILOPENUICCLOGICALCHANNELINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILOPENUICCLOGICALCHANNELINFO {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwChannelId;
  DWORD    dwSelectResponseLength;
  BYTE [1] bSelectResponse;
} RILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwChannelId


### -field dwSelectResponseLength


### -field bSelectResponse


## -remarks
