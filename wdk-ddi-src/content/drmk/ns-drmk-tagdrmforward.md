---
UID: NS:drmk.tagDRMFORWARD
title: tagDRMFORWARD (drmk.h)
description: The DRMFORWARD structure contains the information that the DRMK system driver needs in order to forward a DRM content ID to a device that handles protected content.
old-location: audio\drmforward.htm
tech.root: audio
ms.assetid: 30e2e62a-3ae4-4efe-a6e9-6aece6bfbb46
ms.date: 05/08/2018
ms.keywords: "*PDRMFORWARD, DRMFORWARD, DRMFORWARD structure [Audio Devices], PDRMFORWARD, PDRMFORWARD structure pointer [Audio Devices], aud-prop_491c772b-2e17-42c1-b0cd-68d2b0384163.xml, audio.drmforward, drmk/DRMFORWARD, drmk/PDRMFORWARD, tagDRMFORWARD"
ms.topic: struct
req.header: drmk.h
req.include-header: Drmk.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	drmk.h
api_name:
-	DRMFORWARD
product:
- Windows
targetos: Windows
req.typenames: DRMFORWARD, *PDRMFORWARD
---

# tagDRMFORWARD structure


## -description


The DRMFORWARD structure contains the information that the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">DRMK system driver</a> needs in order to forward a DRM content ID to a device that handles protected content.


## -struct-fields




### -field Flags

No flag bits are currently defined. Set this member to zero.


### -field DeviceObject

Pointer to the device object, which is a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.


### -field FileObject

Pointer to the file object, which is a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>.


### -field Context

Pointer to context data. For more information, see the following Remarks section.


## -remarks



This structure is one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function's call parameters. The structure contains the information that the function needs to send a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request to a WDM driver.

The WDM driver manages the device that is represented by the <b>DeviceObject</b> member. The <b>DrmForwardContentToDeviceObject</b> function sends the property request to this device object.

When constructing the IRP that contains the property request, the <b>DrmForwardContentToDeviceObject</b> function copies the <b>FileObject</b> member into the <b>FileObject</b> field in the driver's I/O stack location in the IRP. If the WDM driver is a KS driver (which implements all or part of a KS filter), the <b>FileObject</b> member represents the pin on the filter that is to receive the stream containing the protected content. For a non-KS driver, the context fields in the FILE_OBJECT structure can contain any value whose meaning is agreed upon between the driver and the caller of the <b>DrmForwardContentToDeviceObject</b> function.

The <b>Context</b> member contains a context value that the <b>DrmForwardContentToDeviceObject</b> function copies into the property descriptor of the KSPROPERTY_DRMAUDIOSTREAM_CONTENTID set-property request (the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537492">KSP_DRMAUDIOSTREAM_CONTENTID</a> structure's <b>Context</b> member). The <b>Context</b> member can contain any value whose meaning is agreed upon between the driver and the caller of the <b>DrmForwardContentToDeviceObject</b> function.

By convention, if the downstream module is a KS filter, the <b>Context</b> member points to a file object that specifies the KS pin to which the <b>DrmForwardContentToDeviceObject</b> function sends the property request. In other words, the <b>Context</b> member points to the same file object as the <b>FileObject</b> member.

The DRMFORWARD structure is also used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537696">PcForwardContentToDeviceObject</a> function and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536579">IDrmPort2::ForwardContentToDeviceObject</a> method, which are alternative entry points for the <b>DrmForwardContentToDeviceObject</b> function. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.

When an audio driver forwards DRM content to a system-supplied USB driver, the following conditions apply: <ul>
<li><b>DRMFORWARD.DeviceObject</b> must be placed at the top of the device stack.</li>
<li><b>DRMFORWARD.FileObject</b> can be <b>NULL</b> because the USB stack does not use IO_STACK_LOCATION.FileObject.</li>
<li><b>DRMFORWARD.Context</b> must be set to a USBD_PIPE_HANDLE value that corresponds to the pipe used by the audio driver.</li>
</ul>


For general information about DRM, see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536579">IDrmPort2::ForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537492">KSP_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537696">PcForwardContentToDeviceObject</a>
 

 

