---
UID: NI:hidport.IOCTL_UMDF_HID_GET_FEATURE
title: IOCTL_UMDF_HID_GET_FEATURE (hidport.h)
description: The IOCTL_UMDF_HID_GET_FEATURE control code obtains a feature report from a HIDClass device.
old-location: hid\ioctl_umdf_hid_get_feature.htm
tech.root: hid
ms.assetid: F22C5B0D-2E8B-4837-AC10-B3CEE56A336D
ms.date: 04/30/2018
ms.keywords: IOCTL_UMDF_HID_GET_FEATURE, IOCTL_UMDF_HID_GET_FEATURE control, IOCTL_UMDF_HID_GET_FEATURE control code, hid.ioctl_umdf_hid_get_feature, hidport/IOCTL_UMDF_HID_GET_FEATURE, umdf.ioctl_umdf_hid_get_feature
ms.topic: ioctl
f1_keywords:
 - "hidport/IOCTL_UMDF_HID_GET_FEATURE"
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
- Hidport.h
api_name:
- IOCTL_UMDF_HID_GET_FEATURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UMDF_HID_GET_FEATURE IOCTL


## -description


The <b>IOCTL_UMDF_HID_GET_FEATURE</b> 
   control code obtains a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/introduction-to-hid-concepts">feature report</a> from a HIDClass device.


## -ioctlparameters




### -input-buffer

A UMDF-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a> to retrieve a requester-allocated input buffer that contains the report ID of the collection.


### -input-buffer-length

The size of the buffer obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a>.


### -output-buffer

A UMDF-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFRequest::GetOutputMemory</a> to retrieve a requester-allocated output buffer. The driver uses the buffer to return a feature report.


### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-setinformation">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidclass/ni-hidclass-ioctl_hid_get_feature">IOCTL_HID_GET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidport/ni-hidport-ioctl_umdf_hid_set_feature">IOCTL_UMDF_HID_SET_FEATURE</a>
 

 

