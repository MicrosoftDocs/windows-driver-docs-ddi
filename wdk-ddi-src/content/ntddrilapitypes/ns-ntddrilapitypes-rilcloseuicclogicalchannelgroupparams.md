---
UID: NS:ntddrilapitypes.RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
title: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcloseuicclogicalchannelgroupparams.htm
old-project: netvista
ms.assetid: 9442df60-7280-4c09-bea0-45ed2ac70694
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCLOSEUICCLOGICALCHANNELGROUPPARAMS structure [Network Drivers Starting with Windows Vista], *LPRILCLOSEUICCLOGICALCHANNELGROUPPARAMS, ntddrilapitypes/RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS, netvista.rilcloseuicclogicalchannelgroupparams
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
-	RILCLOSEUICCLOGICALCHANNELGROUPPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILCLOSEUICCLOGICALCHANNELGROUPPARAMS, RILCLOSEUICCLOGICALCHANNELGROUPPARAMS"
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


