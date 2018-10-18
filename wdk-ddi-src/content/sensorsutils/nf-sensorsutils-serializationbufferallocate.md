---
UID: NF:sensorsutils.SerializationBufferAllocate
title: SerializationBufferAllocate function
author: windows-driver-content
description: Exported memory allocation function for allocating a serialized buffer.
ms.assetid: de91ea34-86fb-42fc-896f-45b2e164b81b
ms.date: 08/08/18
tech.root: sensors
ms.topic: function
ms.keywords: SerializationBufferAllocate
req.header: sensorsutils.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	sensorsutils.h
api_name: 
-	SerializationBufferAllocate
product:
 - Windows
targetos: Windows


---

# SerializationBufferAllocate function


## -description

Exported memory allocation function for allocating a serialized buffer.


## -parameters

### -param SizeInBytes

[in] The size (in bytes) of the buffer to allocate.

### -param pBuffer

[in/out] Pointer to the buffer to allocate.

## -returns

This function returns the following NTSTATUS codes:

* STATUS_NO_MEMORY if there is no more memory.
* STATUS_SUCCESS on success.

## -remarks

## -see-also
