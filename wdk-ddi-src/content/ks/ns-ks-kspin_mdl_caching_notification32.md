---
UID: NS:ks.KSPIN_MDL_CACHING_NOTIFICATION32
title: KSPIN_MDL_CACHING_NOTIFICATION32
author: windows-driver-content
description: This structure is used internally by the operating system.
old-location: stream\kspin_mdl_caching_notification32.htm
old-project: stream
ms.assetid: 36C07734-20FC-4330-8BB1-535E8581162D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSPIN_MDL_CACHING_NOTIFICATION32, ,, 2, 3, A, C, D, F, G, H, I, K, KSPIN_MDL_CACHING_NOTIFICATION32, KSPIN_MDL_CACHING_NOTIFICATION32 structure [Streaming Media Devices], L, M, N, O, P, PKSPIN_MDL_CACHING_NOTIFICATION32, PKSPIN_MDL_CACHING_NOTIFICATION32 structure pointer [Streaming Media Devices], S, T, _, ks/KSPIN_MDL_CACHING_NOTIFICATION32, ks/PKSPIN_MDL_CACHING_NOTIFICATION32, stream.kspin_mdl_caching_notification32"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSPIN_MDL_CACHING_NOTIFICATION32
product: Windows
targetos: Windows
req.typenames: KSPIN_MDL_CACHING_NOTIFICATION32, *PKSPIN_MDL_CACHING_NOTIFICATION32
---

# KSPIN_MDL_CACHING_NOTIFICATION32 structure


## -description


This structure is used internally by the operating system.


## -syntax


````
typedef struct {
  KSPIN_MDL_CACHING_EVENT Event;
  ULONG                   Buffer;
} KSPIN_MDL_CACHING_NOTIFICATION32, *PKSPIN_MDL_CACHING_NOTIFICATION32;
````


## -struct-fields




### -field Event

This member is used internally by the operating system.


### -field Buffer

This member  is used internally by the operating system.

