---
UID: NF:ks.KsAllocateDeviceHeader
title: KsAllocateDeviceHeader function (ks.h)
description: The KsAllocateDeviceHeader function allocates and initializes the required device extension header.
old-location: stream\ksallocatedeviceheader.htm
tech.root: stream
ms.assetid: 554f03bf-cacd-401b-aa34-fcfe1c31091e
ms.date: 04/23/2018
ms.keywords: KsAllocateDeviceHeader, KsAllocateDeviceHeader function [Streaming Media Devices], ks/KsAllocateDeviceHeader, ksfunc_715031de-7d7e-4e24-8e1c-072c7bc271fb.xml, stream.ksallocatedeviceheader
ms.topic: function
f1_keywords:
 - "ks/KsAllocateDeviceHeader"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAllocateDeviceHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAllocateDeviceHeader function

## -description

The **KsAllocateDeviceHeader** function allocates and initializes the required device extension header.

## -parameters

### -param Header [out]

Points to the location in which to return a pointer to the initialized header.

### -param ItemsCount [in]

Specifies the number of subitems in the *ItemsList*. This should be zero if an *ItemsList* is not passed.

### -param ItemsList [in, optional]

Optional. Points to a KSOBJECT_CREATE_ITEM structure for each subitem. If there are no subitems, this value should be **NULL** and *ItemsCount* should be zero.

## -returns

The **KsAllocateDeviceHeader** function returns STATUS_SUCCESS if successful or STATUS_INSUFFICIENT_RESOURCES if unable to allocate the necessary resources.

## -remarks

The **KsAllocateDeviceHeader** function allocates memory for the KSDEVICE_HEADER structure for a device. When the header is no longer needed, the driver should call the **KsFreeDeviceHeader** function to free the memory allocated.

If subobjects exist for a given device, the driver must, before calling **KsAllocateDeviceHeader**, allocate a buffer of either paged or nonpaged memory of sufficient size to hold a KSOBJECT_CREATE_ITEM structure for each subobject. For example:

```cpp
/* Allocate a buffer for 4 subobjects for a given streaming device */
PKSOBJECT_CREATE_ITEM createBuffer ;
ULONG bufferSize  = (sizeof (KSOBJECT_CREATE_ITEM)) * 4 ;

createBuffer = (PKSOBJECT_CREATE_ITEM)
               ExAllocatePoolWithTag (PagedPool, bufferSize) ;
```

Drivers must not free the memory allocated for the subobject KSOBJECT_CREATE_ITEM list until after calling **KsFreeDeviceHeader**. Failure to do so can result in a bug check condition.

## -see-also

[KSOBJECT_CREATE_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksobject_create_item)

[KsFreeDeviceHeader](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksfreedeviceheader)
