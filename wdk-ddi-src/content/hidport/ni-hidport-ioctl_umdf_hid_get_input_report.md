---
UID: NI:hidport.IOCTL_UMDF_HID_GET_INPUT_REPORT
title: IOCTL_UMDF_HID_GET_INPUT_REPORT
author: windows-driver-content
description: The IOCTL_UMDF_HID_GET_INPUT_REPORT control code returns an input report from a HIDClass device.
old-location: hid\ioctl_umdf_hid_get_input_report.htm
old-project: hid
ms.assetid: 05BA5290-33D5-4009-98EE-E530546C44D3
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IOCTL_UMDF_HID_GET_INPUT_REPORT
req.alt-loc: Hidport.h
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
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_UMDF_HID_GET_INPUT_REPORT IOCTL



## -description
The <b>IOCTL_UMDF_HID_GET_INPUT_REPORT</b> 
   control code returns an <a href="https://msdn.microsoft.com/477FF911-5A17-4EA5-9403-1D7B4E8B3BA5">input report</a> from a HIDClass device.



## -ioctlparameters

### -input-buffer
A UMDF-based driver calls <a href="https://msdn.microsoft.com/be3f965b-69fe-4d5e-b1b6-3a370603cd7b">IWDFRequest::GetInputMemory</a> to retrieve a memory buffer that contains the report ID of the collection.


### -input-buffer-length
The size of the buffer retrieved by calling <a href="https://msdn.microsoft.com/be3f965b-69fe-4d5e-b1b6-3a370603cd7b">IWDFRequest::GetInputMemory</a>.


### -output-buffer
A UMDF-based driver calls <a href="https://msdn.microsoft.com/12862fb2-4cdb-4446-aa20-ec911c9cd65f">IWDFRequest::GetOutputMemory</a> to retrieve a requester-allocated output buffer that it uses to return a feature report.


### -output-buffer-length
The size of the buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
HID minidrivers that carry out the I/O to the device must also:


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439672">IOCTL_UMDF_HID_SET_OUTPUT_REPORT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\wdf]:%20IOCTL_UMDF_HID_GET_INPUT_REPORT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

