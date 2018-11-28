---
UID: NF:sensorsutils.CollectionsListUpdateMarshalledPointer
title: CollectionsListUpdateMarshalledPointer function
author: windows-driver-content
description: This routine update embedded pointers.
ms.assetid: f4e07e07-4f80-4427-b073-ea6f38346db5
ms.date: 08/08/2018
tech.root: sensors
ms.topic: function
ms.keywords: CollectionsListUpdateMarshalledPointer
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
-	CollectionsListUpdateMarshalledPointer
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# CollectionsListUpdateMarshalledPointer function


## -description

This routine update embedded pointers. It should be called when marshalled collection list pass between processes.

> [!WARNING]
> This method assumes the structure sizes stay the same during marshalling. Avoid using this method if passing the data between processes that can have different bit-ness values (e.g. 32 bit <-> 64 bit). Use CollectionsListDeserializeFromBuffer instead.



## -parameters

### -param Collection

[in/out] A pointer to a sensor collection list.

## -returns

This function returns STATUS_INVALID_PARAMETER if:

* The Collection is null.
* The AllocatedSizeInBytes member of Collection is less than the acceptable minimum size (in bytes) for a sensor collection list. 

Returns STATUS_SUCCESS otherwise.

## -remarks

## -see-also
