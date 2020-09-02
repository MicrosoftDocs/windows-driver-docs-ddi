---
UID: NI:hidport.IOCTL_UMDF_HID_GET_INPUT_REPORT
title: IOCTL_UMDF_HID_GET_INPUT_REPORT (hidport.h)
description: The IOCTL_UMDF_HID_GET_INPUT_REPORT control code returns an input report from a HIDClass device.
old-location: hid\ioctl_umdf_hid_get_input_report.htm
tech.root: hid
ms.assetid: 05BA5290-33D5-4009-98EE-E530546C44D3
ms.date: 04/30/2018
keywords: ["IOCTL_UMDF_HID_GET_INPUT_REPORT IOCTL"]
ms.keywords: IOCTL_UMDF_HID_GET_INPUT_REPORT, IOCTL_UMDF_HID_GET_INPUT_REPORT control, IOCTL_UMDF_HID_GET_INPUT_REPORT control code, hid.ioctl_umdf_hid_get_input_report, hidport/IOCTL_UMDF_HID_GET_INPUT_REPORT, umdf.ioctl_umdf_hid_get_input_report
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_UMDF_HID_GET_INPUT_REPORT
 - hidport/IOCTL_UMDF_HID_GET_INPUT_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hidport.h
api_name:
 - IOCTL_UMDF_HID_GET_INPUT_REPORT
---

# IOCTL_UMDF_HID_GET_INPUT_REPORT IOCTL


## -description

The <b>IOCTL_UMDF_HID_GET_INPUT_REPORT</b> 
   control code returns an <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/introduction-to-hid-concepts">input report</a> from a HIDClass device.

## -ioctlparameters

### -input-buffer

A UMDF-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a> to retrieve a memory buffer that contains the report ID of the collection.

### -input-buffer-length

The size of the buffer retrieved by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a>.

### -output-buffer

A UMDF-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFRequest::GetOutputMemory</a> to retrieve a requester-allocated output buffer that it uses to return a feature report.

### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-setinformation">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report">IOCTL_HID_GET_INPUT_REPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_umdf_hid_set_output_report">IOCTL_UMDF_HID_SET_OUTPUT_REPORT</a>

