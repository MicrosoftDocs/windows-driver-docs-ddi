---
UID: NS:rilapitypes.RILVERSIONPARAMS
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams_2.htm
old-project: netvista
ms.assetid: 365230b4-fd09-413f-9174-a5c5576a9160
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILVERSIONPARAMS, RILVERSIONPARAMS, RILVERSIONPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilversionparams_2, rilapitypes/RILVERSIONPARAMS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILVERSIONPARAMS
product: Windows
targetos: Windows
req.typenames: RILVERSIONPARAMS, *LPRILVERSIONPARAMS
req.product: Windows 10 or later.
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

