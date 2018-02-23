---
UID: NS:ntddrilapitypes.RILVERSIONPARAMS
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams.htm
old-project: netvista
ms.assetid: c6931cee-2b86-4bf8-9e9d-b04e2df9eb12
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilversionparams, *LPRILVERSIONPARAMS, ntddrilapitypes/RILVERSIONPARAMS, RILVERSIONPARAMS structure [Network Drivers Starting with Windows Vista], RILVERSIONPARAMS
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
-	RILVERSIONPARAMS
product: Windows
targetos: Windows
req.typenames: RILVERSIONPARAMS, *LPRILVERSIONPARAMS
---

# RILVERSIONPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILVERSIONPARAMS {
  WORD  Minor;
  WORD  Major;
} RILVERSIONPARAMS, RILVERSIONPARAMS;
````


## -struct-fields




### -field Minor


### -field Major

