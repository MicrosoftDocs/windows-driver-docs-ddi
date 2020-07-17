---
UID: NF:minitape.TapeClassAllocateSrbBuffer
title: TapeClassAllocateSrbBuffer function (minitape.h)
description: The TapeClassAllocateSrbBuffer routine allocates an Srb->DataBuffer.
old-location: storage\tapeclassallocatesrbbuffer.htm
tech.root: storage
ms.assetid: f6762d9b-5a3d-49a3-b954-48e4e4a9eacb
ms.date: 03/29/2018
keywords: ["TapeClassAllocateSrbBuffer function"]
ms.keywords: TapeClassAllocateSrbBuffer, TapeClassAllocateSrbBuffer routine [Storage Devices], minitape/TapeClassAllocateSrbBuffer, storage.tapeclassallocatesrbbuffer, tapeclas_77717175-fd25-4cbe-8baf-8c326a5ec152.xml
f1_keywords:
 - "minitape/TapeClassAllocateSrbBuffer"
 - "TapeClassAllocateSrbBuffer"
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
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
req.lib: Tape.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Tape.lib
- Tape.dll
api_name:
- TapeClassAllocateSrbBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# TapeClassAllocateSrbBuffer function


## -description


The <b>TapeClassAllocateSrbBuffer</b> routine allocates an <b>Srb->DataBuffer</b>.


## -parameters




### -param Srb [in, out]

Pointer to the SRB.


### -param SrbBufferSize [in]

Specifies the size, in bytes, of the <b>DataBuffer</b> to be allocated.


## -returns



<b>TapeClassAllocateSrbBuffer </b>returns <b>TRUE</b> if the <b>DataBuffer</b> was allocated successfully, and <b>FALSE</b> if the buffer was not allocated.




## -remarks



<b>TapeClassAllocateSrbBuffer </b>allocates an <b>Srb->DataBuffer</b> from nonpaged memory and initializes the members to zero. If the buffer already exists from an earlier call, it is freed and a new buffer allocated. A tape miniclass driver calls this routine to allocate a <b>DataBuffer</b> in a portable way.



