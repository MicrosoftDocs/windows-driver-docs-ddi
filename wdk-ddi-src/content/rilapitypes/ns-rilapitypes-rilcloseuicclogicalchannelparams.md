---
UID: NS:rilapitypes.RILCLOSEUICCLOGICALCHANNELPARAMS
title: RILCLOSEUICCLOGICALCHANNELPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcloseuicclogicalchannelparams_2.htm
old-project: netvista
ms.assetid: 4e7d2a46-b31e-4ead-8918-b6da970eb7c9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcloseuicclogicalchannelparams_2, rilapitypes/RILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS
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
-	RILCLOSEUICCLOGICALCHANNELPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS"
req.product: Windows 10 or later.
---

# RILCLOSEUICCLOGICALCHANNELPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCLOSEUICCLOGICALCHANNELPARAMS {
  DWORD  dwSlotIndex;
  DWORD  dwChannelId;
} RILCLOSEUICCLOGICALCHANNELPARAMS, RILCLOSEUICCLOGICALCHANNELPARAMS;
````


## -struct-fields




### -field dwSlotIndex


### -field dwChannelId

