---
UID: NF:acxstreams.AcxDrmForwardContentToDeviceObject
tech.root: audio
title: AcxDrmForwardContentToDeviceObject
ms.date: 07/01/2021
targetos: Windows
description: The AcxDrmForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef 
api_location:
 - acxstreams.h
api_name:
 - AcxDrmForwardContentToDeviceObject
f1_keywords:
 - AcxDrmForwardContentToDeviceObject
 - acxstreams/AcxDrmForwardContentToDeviceObject
dev_langs:
 - c++
---

## -description

The AcxDrmForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content. The function authenticates the device and sends it the content ID and DRM rights that the system has assigned to the protected content.

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to a KS  (ACX?) audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


### -param Reserved

Reserved for future use. Set to NULL.

### -param DrmForward

Pointer to an [ACXDRMFORWARD structure](ns-acxstreams-acxdrmforward.md) specifying a device object and file object that identify the target device and a KS audio pin on that device, respectively. The structure also contains the context value that the [KSPROPERTY_DRMAUDIOSTREAM_CONTENTID](/windows-hardware/drivers/ddi/drmk/ns-drmk-ksp_drmaudiostream_contentid) set-property request passes to the device.

## -returns

AcxDrmForwardContentToDeviceObject returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks


### Example

TBD - no sample driver code found

Example usage is shown below.

```cpp

```

## -see-also

[acxstreams.h header](index.md)

