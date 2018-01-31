---
UID: NS:rilapitypes.RILOPENUICCLOGICALCHANNELINFO
title: RILOPENUICCLOGICALCHANNELINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelinfo_2.htm
old-project: netvista
ms.assetid: f731c790-4348-4c18-aef1-184c3d4bf258
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILOPENUICCLOGICALCHANNELINFO, netvista.rilopenuicclogicalchannelinfo_2, RILOPENUICCLOGICALCHANNELINFO structure [Network Drivers Starting with Windows Vista], RILOPENUICCLOGICALCHANNELINFO, *LPRILOPENUICCLOGICALCHANNELINFO
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
-	RILOPENUICCLOGICALCHANNELINFO
product: Windows
targetos: Windows
req.typenames: "*LPRILOPENUICCLOGICALCHANNELINFO, RILOPENUICCLOGICALCHANNELINFO"
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




#### - cbSize



#### - dwParams



#### - dwChannelId



#### - dwSelectResponseLength



#### - bSelectResponse


