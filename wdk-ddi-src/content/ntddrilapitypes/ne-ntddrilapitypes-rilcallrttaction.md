---
UID: NE:ntddrilapitypes.RILCALLRTTACTION
title: RILCALLRTTACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallrttaction.htm
old-project: netvista
ms.assetid: c080c4da-097d-4ae3-b1ca-96d9b5b6e8c9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLRTTACTION, RILCALLRTTACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLRTTACTION
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
req.typenames: RILCALLRTTACTION
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
