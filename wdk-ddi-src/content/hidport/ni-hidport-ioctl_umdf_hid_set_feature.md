---
UID: NI:hidport.IOCTL_UMDF_HID_SET_FEATURE
title: IOCTL_UMDF_HID_SET_FEATURE (hidport.h)
description: The IOCTL_UMDF_HID_GET_FEATURE control code sends a feature report to a HIDClass device.
old-location: hid\ioctl_umdf_hid_set_feature.htm
tech.root: hid
ms.assetid: 7FFE7301-1C03-4221-9E3B-412FE89919FB
ms.date: 04/30/2018
ms.keywords: IOCTL_UMDF_HID_SET_FEATURE, IOCTL_UMDF_HID_SET_FEATURE control, IOCTL_UMDF_HID_SET_FEATURE control code, hid.ioctl_umdf_hid_set_feature, hidport/IOCTL_UMDF_HID_SET_FEATURE, umdf.ioctl_umdf_hid_set_feature
f1_keywords:
 - "hidport/IOCTL_UMDF_HID_SET_FEATURE"
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
- IOCTL_UMDF_HID_SET_FEATURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UMDF_HID_SET_FEATURE IOCTL


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_umdf_hid_get_feature">IOCTL_UMDF_HID_GET_FEATURE</a> 
   control code sends a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/introduction-to-hid-concepts">feature report</a> to a HIDClass device.


## -ioctlparameters




### -input-buffer

A UMDF-based driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFRequest::GetInputMemory</a> to retrieve a  requester-allocated input buffer that contains a feature report.

The driver retrieves the report ID associated with the top-level collection by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getdeviceiocontrolparameters">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter, as shown in the following example.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UCHAR reportId;
SIZE_T outBufferSize;

FxRequest->GetDeviceIoControlParameters(NULL, NULL, &outBufferSize);
reportId = (UCHAR)outBufferSize;
</pre>
</td>
</tr>
</table></span></div>



### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

The size of the buffer that is retrieved by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-setinformation">IWDFRequest::SetInformation</a> to set the number of bytes transferred to the device.</li>
<li>Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature">IOCTL_HID_SET_FEATURE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidport/ni-hidport-ioctl_umdf_hid_get_feature">IOCTL_UMDF_HID_GET_FEATURE</a>
 

 

