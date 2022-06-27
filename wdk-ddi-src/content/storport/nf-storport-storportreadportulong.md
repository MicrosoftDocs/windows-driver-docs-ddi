---
UID: NF:storport.StorPortReadPortUlong
title: StorPortReadPortUlong macro (storport.h)
description: The StorPortReadPortUlong routine reads a value from a specified port address.
old-location: storage\storportreadportulong.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["StorPortReadPortUlong macro"]
ms.keywords: StorPortReadPortUlong, StorPortReadPortUlong routine [Storage Devices], storage.storportreadportulong, storport/StorPortReadPortUlong, storprt_3ef5c577-3d75-4797-b5ce-8f36e4080c47.xml
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
 - StorPortReadPortUlong
 - storport/StorPortReadPortUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortReadPortUlong
---

# StorPortReadPortUlong macro

## -description

The **StorPortReadPortUlong** routine reads a value from a specified port address.

## -parameters

### -param h [in]

A pointer to the hardware device extension.

### -param p [in]

A pointer to the address from which to read.

## -remarks

For more information, see the [**ScsiPortReadPortUlong**](../srb/nf-srb-scsiportreadportulong.md) routine. For a buffered version of this routine see [**StorPortReadPortBufferUlong**](nf-storport-storportreadportbufferulong.md).
