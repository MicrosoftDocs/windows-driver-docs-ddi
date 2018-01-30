---
UID: NS:ntddrilapitypes.RILOPENUICCLOGICALCHANNELPARAMS
title: RILOPENUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilopenuicclogicalchannelparams.htm
old-project: netvista
ms.assetid: 4bc3a16b-dc9e-4c15-9083-75ac4608def5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilopenuicclogicalchannelparams, ntddrilapitypes/RILOPENUICCLOGICALCHANNELPARAMS, *LPRILOPENUICCLOGICALCHANNELPARAMS
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
-	RILOPENUICCLOGICALCHANNELPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS"
---

# RILOPENUICCLOGICALCHANNELPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILOPENUICCLOGICALCHANNELPARAMS {
  DWORD     dwSlotIndex;
  DWORD     dwChannelGroup;
  DWORD     dwAppIdLength;
  BYTE [32] bAppId;
  DWORD     dwSelectP2Arg;
} RILOPENUICCLOGICALCHANNELPARAMS, RILOPENUICCLOGICALCHANNELPARAMS;
````


## -struct-fields




### -field dwSlotIndex



### -field dwChannelGroup



### -field dwAppIdLength



### -field bAppId



### -field dwSelectP2Arg


