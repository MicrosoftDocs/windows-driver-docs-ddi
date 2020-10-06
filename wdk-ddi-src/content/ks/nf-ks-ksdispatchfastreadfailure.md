---
UID: NF:ks.KsDispatchFastReadFailure
title: KsDispatchFastReadFailure function (ks.h)
description: The KsDispatchFastReadFailure function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return FALSE.
old-location: stream\ksdispatchfastreadfailure.htm
tech.root: stream
ms.assetid: 7e0c72ce-0959-4835-ac1a-3f37869cc81f
ms.date: 04/23/2018
keywords: ["KsDispatchFastReadFailure function"]
ms.keywords: KsDispatchFastReadFailure, KsDispatchFastReadFailure function [Streaming Media Devices], KsDispatchFastWriteFailure, ks/KsDispatchFastReadFailure, ksfunc_fe3ea42f-80ae-4fbd-a2c2-55e957e913cc.xml, stream.ksdispatchfastreadfailure
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDispatchFastReadFailure
 - ks/KsDispatchFastReadFailure
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDispatchFastReadFailure
---

# KsDispatchFastReadFailure function


## -description

The <b>KsDispatchFastReadFailure</b> function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return <b>FALSE</b>.

## -parameters

### -param FileObject 

[in]
Not used.

### -param FileOffset 

[in]
Not used.

### -param Length 

[in]
Not used.

### -param Wait 

[in]
Not used.

### -param LockKey 

[in]
Not used.

### -param Buffer 

[out]
Not used.

### -param IoStatus 

[out]
Not used.

### -param DeviceObject 

[in]
Not used.

## -returns

The <b>KsDispatchFastReadFailure</b> function returns <b>FALSE</b>.

## -remarks

The <b>KsDispatchFastReadFailure</b> function is needed since the dispatch table for a particular opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function, such as the <b>KsDispatchFastReadFailure</b> function, that calls a dispatch table entry.

