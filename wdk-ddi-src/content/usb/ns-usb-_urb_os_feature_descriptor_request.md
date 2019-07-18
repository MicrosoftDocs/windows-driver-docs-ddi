---
UID: NS:usb._URB_OS_FEATURE_DESCRIPTOR_REQUEST
title: _URB_OS_FEATURE_DESCRIPTOR_REQUEST (usb.h)
description: The _URB_OS_FEATURE_DESCRIPTOR_REQUEST structure is used by the USB hub driver to retrieve Microsoft OS Feature Descriptors from a USB device or an interface on a USB device.
old-location: buses\_urb_os_feature_descriptor_request.htm
tech.root: usbref
ms.assetid: 9ff62523-e9e3-4f32-802f-6fee0082d925
ms.date: 05/07/2018
ms.keywords: "_URB_OS_FEATURE_DESCRIPTOR_REQUEST, _URB_OS_FEATURE_DESCRIPTOR_REQUEST structure [Buses], buses._urb_os_feature_descriptor_request, usb/_URB_OS_FEATURE_DESCRIPTOR_REQUEST"
ms.topic: struct
f1_keywords:
 - "usb/_URB_OS_FEATURE_DESCRIPTOR_REQUEST"
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usb.h
api_name:
- _URB_OS_FEATURE_DESCRIPTOR_REQUEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# _URB_OS_FEATURE_DESCRIPTOR_REQUEST structure


## -description


The <b>_URB_OS_FEATURE_DESCRIPTOR_REQUEST</b> structure is used by the USB hub driver to retrieve Microsoft OS Feature Descriptors from a USB device or an interface on a USB device.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must URB_FUNCTION_GET_MS_FEATURE_DESCRIPTOR.
<b>Hdr.Length</b> must be <code>sizeof(_URB_OS_FEATURE_DESCRIPTOR_REQUEST)</code>.



### -field Reserved

 


### -field Reserved0

 


### -field TransferBufferLength

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes read in this member.  Current implementation of this function limits the maximum MS OS Feature Descriptor size to 4 Kilobytes.


### -field TransferBuffer

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. 


### -field TransferBufferMDL

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. This MDL must be allocated from nonpaged pool.


### -field UrbLink

Reserved. Do not use.


### -field hca

 


### -field Recipient

Specifies whether the recipient is the USB device or an interface on the USB device.  One of the following values must be specified:

<ul>
<li>0 indicates that the USB device is the recipient of the request.
</li>
<li>1 indicates that a USB interface is the recipient of the request. 
</li>
<li>2 indicates that a USB endpoint is the recipient of the request. 
</li>
</ul>

### -field Reserved1

 


### -field Reserved2

 


### -field InterfaceNumber

Indicates the interface number that is the recipient of the request, if the <b>Recipient</b> member value is 1. Must be set to 0 if the USB device is the recipient.


### -field MS_PageIndex

Must be set to 0. Page index of the 64K page of the MS OS Feature Descriptor to be returned.  Current implementation only supports a maximum descriptor size of 4K.


### -field MS_FeatureDescriptorIndex

Index for MS OS Feature Descriptor to be requested.


### -field Reserved3

 




## -remarks



The reserved members of this structure must be treated as opaque and are reserved for system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_header">_URB_HEADER</a>
 

 

