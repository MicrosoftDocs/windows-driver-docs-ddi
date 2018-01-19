---
UID: NE:rilapitypes.RILCALLRTTACTION
title: RILCALLRTTACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrttaction_2.htm
old-project: netvista
ms.assetid: e4a28382-25f9-427d-ba7a-3b35c01f50fd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLRTTACTION, RILCALLRTTACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLRTTACTION
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
req.typenames: RILCALLRTTACTION
req.product: Windows 10 or later.
---

# RILCALLRTTACTION enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILCALLRTTACTION { 
  RIL_CALLRTTACTION_REJECT,
  RIL_CALLRTTACTION_ASK,
  RIL_CALLRTTACTION_ACCEPT,
  RIL_CALLRTTACTION_MAX
} RILCALLRTTACTION;
````


## -enum-fields

### -field RIL_CALLRTTACTION_REJECT


### -field RIL_CALLRTTACTION_ASK


### -field RIL_CALLRTTACTION_ACCEPT


### -field RIL_CALLRTTACTION_MAX


## -remarks
