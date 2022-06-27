---
UID: NF:storport.StorPortReadRegisterBufferUshort
title: StorPortReadRegisterBufferUshort macro (storport.h)
description: The StorPortReadRegisterBufferUshort routine reads a value from a specified register address.
old-location: storage\storportreadregisterbufferushort.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["StorPortReadRegisterBufferUshort macro"]
ms.keywords: StorPortReadRegisterBufferUshort, StorPortReadRegisterBufferUshort routine [Storage Devices], storage.storportreadregisterbufferushort, storport/StorPortReadRegisterBufferUshort, storprt_9ba740e5-78b0-464d-903c-6bb4c22788fd.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortReadRegisterBufferUshort
 - storport/StorPortReadRegisterBufferUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortReadRegisterBufferUshort
---

# StorPortReadRegisterBufferUshort macro

## -description

The **StorPortReadRegisterBufferUshort** routine reads a value from a specified register address.

## -parameters

### -param h [in]

A pointer to the hardware device extension.

### -param r [in]

A pointer to the register where the data is to be read.

### -param b [in]

A pointer to the buffer that receives the data that is read.

### -param c [in]

The number of data items to be read. Each data item has a size of ```sizeof(USHORT)```.

## -remarks

For more information, see [**ScsiPortReadRegisterBufferUshort**](../srb/nf-srb-scsiportreadregisterbufferushort.md). For a nonbuffered version of this routine, see [**StorPortReadRegisterUshort**](nf-storport-storportreadregisterushort.md).
