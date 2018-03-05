---
UID: NF:portcls.PcForwardContentToDeviceObject
title: PcForwardContentToDeviceObject function
author: windows-driver-content
description: The PcForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttodeviceobject.htm
old-project: audio
ms.assetid: 24891f90-422f-4104-97f4-395205e2b862
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PcForwardContentToDeviceObject, PcForwardContentToDeviceObject function [Audio Devices], audio.pcforwardcontenttodeviceobject, audpc-routines_1dec7e58-07b2-41ce-82d3-5f0670bbc273.xml, portcls/PcForwardContentToDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcForwardContentToDeviceObject
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcForwardContentToDeviceObject function


## -description


The <b>PcForwardContentToDeviceObject</b> function accepts a device object representing a device to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function, and its parameter definitions and return value are also identical.


## -syntax


````
PORTCLASSAPI NTSTATUS NTAPI PcForwardContentToDeviceObject(
  _In_     ULONG        ContentId,
  _In_opt_ PVOID        Reserved,
  _In_     PCDRMFORWARD DrmForward
);
````


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.


### -param Reserved [in, optional]

Reserved for future use. Set to <b>NULL</b>.


### -param DrmForward [in]

Pointer to a <a href="..\drmk\ns-drmk-tagdrmforward.md">DRMFORWARD</a> structure specifying a device object and file object that identify the target device and a KS audio pin on that device, respectively. The structure also contains the context value that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request passes to the device.


## -returns



See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>.




## -remarks



For more information, see the comments in <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>.




## -see-also

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcForwardContentToDeviceObject function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

