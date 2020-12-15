---
UID: NI:hidport.IOCTL_UMDF_HID_SET_OUTPUT_REPORT
title: IOCTL_UMDF_HID_SET_OUTPUT_REPORT (hidport.h)
description: The IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code sends an output report to a top-level collection.
old-location: hid\ioctl_umdf_hid_set_output_report.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["IOCTL_UMDF_HID_SET_OUTPUT_REPORT IOCTL"]
ms.keywords: IOCTL_UMDF_HID_SET_OUTPUT_REPORT, IOCTL_UMDF_HID_SET_OUTPUT_REPORT control, IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code, hid.ioctl_umdf_hid_set_output_report, hidport/IOCTL_UMDF_HID_SET_OUTPUT_REPORT, umdf.ioctl_umdf_hid_set_output_report
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
 - IOCTL_UMDF_HID_SET_OUTPUT_REPORT
 - hidport/IOCTL_UMDF_HID_SET_OUTPUT_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hidport.h
api_name:
 - IOCTL_UMDF_HID_SET_OUTPUT_REPORT
---

# IOCTL_UMDF_HID_SET_OUTPUT_REPORT IOCTL


## -description

The <b>IOCTL_UMDF_HID_SET_OUTPUT_REPORT</b> 
   control code sends an <a href="/windows-hardware/drivers/hid/introduction-to-hid-concepts">output report</a> to a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.

## -ioctlparameters

### -input-buffer

A UMDF-based driver calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a> to retrieve a  requester-allocated input buffer that contains an output report. 


The driver retrieves the report ID associated with the top-level collection by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getdeviceiocontrolparameters">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter, as shown in the following example.
```
UCHAR reportId;
SIZE_T outBufferSize;

FxRequest->GetDeviceIoControlParameters(NULL, NULL, &outBufferSize);
reportId = (UCHAR)outBufferSize;

```


### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-setinformation">IWDFRequest::SetInformation</a> to set the number of bytes transferred to the device.</li>
<li>Call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report">IOCTL_HID_SET_OUTPUT_REPORT</a>



<a href="/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_umdf_hid_get_input_report">IOCTL_UMDF_HID_GET_INPUT_REPORT</a>
