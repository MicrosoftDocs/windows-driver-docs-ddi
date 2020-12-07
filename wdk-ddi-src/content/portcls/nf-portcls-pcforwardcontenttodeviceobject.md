---
UID: NF:portcls.PcForwardContentToDeviceObject
title: PcForwardContentToDeviceObject function (portcls.h)
description: The PcForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttodeviceobject.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcForwardContentToDeviceObject function"]
ms.keywords: PcForwardContentToDeviceObject, PcForwardContentToDeviceObject function [Audio Devices], audio.pcforwardcontenttodeviceobject, audpc-routines_1dec7e58-07b2-41ce-82d3-5f0670bbc273.xml, portcls/PcForwardContentToDeviceObject
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToDeviceObject function in Microsoft Windows XP and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PcForwardContentToDeviceObject
 - portcls/PcForwardContentToDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcForwardContentToDeviceObject
---

# PcForwardContentToDeviceObject function


## -description

The <b>PcForwardContentToDeviceObject</b> function accepts a device object representing a device to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a> function, and its parameter definitions and return value are also identical.

## -parameters

### -param ContentId 

[in]
Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

### -param Reserved 

[in, optional]
Reserved for future use. Set to <b>NULL</b>.

### -param DrmForward 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/drmk/ns-drmk-tagdrmforward">DRMFORWARD</a> structure specifying a device object and file object that identify the target device and a KS audio pin on that device, respectively. The structure also contains the context value that the <a href="/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request passes to the device.

## -returns

See return value definition in <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>.

## -remarks

For more information, see the comments in <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>
