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
ms.keywords: hid.ioctl_umdf_hid_get_input_report, IOCTL_UMDF_HID_GET_INPUT_REPORT control code, IOCTL_UMDF_HID_GET_INPUT_REPORT, hidport/IOCTL_UMDF_HID_GET_INPUT_REPORT, umdf.ioctl_umdf_hid_get_input_report
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hidport.h
apiname:
-	IOCTL_UMDF_HID_GET_INPUT_REPORT
product: Windows
targetos: Windows
req.typenames: "*PUSAGE_AND_PAGE, USAGE_AND_PAGE"
---

# IOCTL_UMDF_HID_GET_INPUT_REPORT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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

HID minidrivers that carry out the I/O to the device must also:
<ul>
<li>Call <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="https://msdn.microsoft.com/2fa389f8-8277-4795-a89e-ac5d92004310">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439672">IOCTL_UMDF_HID_SET_OUTPUT_REPORT</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\wdf]:%20IOCTL_UMDF_HID_GET_INPUT_REPORT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

