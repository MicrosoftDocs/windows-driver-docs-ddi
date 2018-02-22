---
UID: NS:ks.KSSTREAMALLOCATOR_STATUS_EX
title: KSSTREAMALLOCATOR_STATUS_EX
author: windows-driver-content
description: Client use KSSTREAMALLOCATOR_STATUS_EX to query the status for allocators supporting the extended allocator framing.
old-location: stream\ksstreamallocator_status_ex.htm
old-project: stream
ms.assetid: b0477c52-d9e6-47cd-b94c-b9da2c4e07a6
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/PKSSTREAMALLOCATOR_STATUS_EX, *PKSSTREAMALLOCATOR_STATUS_EX, PKSSTREAMALLOCATOR_STATUS_EX structure pointer [Streaming Media Devices], PKSSTREAMALLOCATOR_STATUS_EX, ks-struct_e62b6482-11b5-48be-9263-719809e9e79d.xml, ks/KSSTREAMALLOCATOR_STATUS_EX, KSSTREAMALLOCATOR_STATUS_EX, stream.ksstreamallocator_status_ex, KSSTREAMALLOCATOR_STATUS_EX structure [Streaming Media Devices]
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
-	KSSTREAMALLOCATOR_STATUS_EX
product: Windows
targetos: Windows
req.typenames: "*PKSSTREAMALLOCATOR_STATUS_EX, KSSTREAMALLOCATOR_STATUS_EX"
---

# KSSTREAMALLOCATOR_STATUS_EX structure


## -description


Client use KSSTREAMALLOCATOR_STATUS_EX to query the status for allocators supporting the extended allocator framing.


## -syntax


````
typedef struct {
  KSALLOCATOR_FRAMING_EX Framing;
  ULONG                  AllocatedFrames;
  ULONG                  Reserved;
} KSSTREAMALLOCATOR_STATUS_EX, *PKSSTREAMALLOCATOR_STATUS_EX;
````


## -struct-fields




### -field Framing

Contains the framing specified when the allocator was created.


### -field AllocatedFrames

Contains the current number of allocated frames.


### -field Reserved

Reserved and set to zero.


## -remarks



KSSTREAMALLOCATOR_STATUS_EX corresponds closely to KSSTREAMALLOCATOR_STATUS except that instead of passing back a KSALLOCATOR_FRAMING, it passes back the extended structure.



