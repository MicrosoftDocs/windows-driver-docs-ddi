---
UID: NS:rilapitypes.RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
title: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcloseuicclogicalchannelgroupparams_2.htm
old-project: netvista
ms.assetid: 89d50918-2cd2-4889-aec4-fc9e2875855a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilcloseuicclogicalchannelgroupparams_2, *LPRILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
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
-	RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
product: Windows
targetos: Windows
req.typenames: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, *LPRILCLOSEUICCLOGICALCHANNELGROUPPARAMS
req.product: Windows 10 or later.
---

# RILCLOSEUICCLOGICALCHANNELGROUPPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCLOSEUICCLOGICALCHANNELGROUPPARAMS {
  DWORD  dwSlotIndex;
  DWORD  dwChannelGroup;
} RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS;
````


## -struct-fields




### -field dwSlotIndex



### -field dwChannelGroup


