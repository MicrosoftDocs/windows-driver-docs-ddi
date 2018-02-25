---
UID: NS:bdatypes._BDA_BUFFER
title: "_BDA_BUFFER"
author: windows-driver-content
description: "."
old-location: stream\bda_buffer.htm
old-project: stream
ms.assetid: DCC7087B-0A1B-4E96-A82F-BDEF09D8CEE2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PBDA_BUFFER, ,, A, B, BDA_BUFFER, BDA_BUFFER structure [Streaming Media Devices], D, E, F, P, PBDA_BUFFER, PBDA_BUFFER structure pointer [Streaming Media Devices], R, U, _, _BDA_BUFFER, bdatypes/BDA_BUFFER, bdatypes/PBDA_BUFFER, stream.bda_buffer"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_BUFFER
product: Windows
targetos: Windows
req.typenames: BDA_BUFFER, *PBDA_BUFFER
---

# _BDA_BUFFER structure


## -description





## -syntax


````
typedef struct _BDA_BUFFER {
  PBDARESULT lResult;
  ULONG      ulKeyuuidBufferLen;
  GUID       argKeyuuidBuffer[MIN_DIMENSION];
} BDA_BUFFER, *PBDA_BUFFER;
````


## -struct-fields




### -field lResult


### -field ulBufferSize

 


### -field argbBuffer

 




#### - ulKeyuuidBufferLen


#### - argKeyuuidBuffer

