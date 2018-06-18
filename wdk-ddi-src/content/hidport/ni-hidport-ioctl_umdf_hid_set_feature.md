---
UID: NI:hidport.IOCTL_UMDF_HID_SET_FEATURE
title: IOCTL_UMDF_HID_SET_FEATURE
author: windows-driver-content
description: The IOCTL_UMDF_HID_GET_FEATURE control code sends a feature report to a HIDClass device.
old-location: hid\ioctl_umdf_hid_set_feature.htm
old-project: hid
ms.assetid: 7FFE7301-1C03-4221-9E3B-412FE89919FB
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_UMDF_HID_SET_FEATURE, IOCTL_UMDF_HID_SET_FEATURE control, IOCTL_UMDF_HID_SET_FEATURE control code, hid.ioctl_umdf_hid_set_feature, hidport/IOCTL_UMDF_HID_SET_FEATURE, umdf.ioctl_umdf_hid_set_feature
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hidport.h
api_name:
-	IOCTL_UMDF_HID_SET_FEATURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_UMDF_HID_SET_FEATURE IOCTL


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439657">IOCTL_UMDF_HID_GET_FEATURE</a> 
   control code sends a <a href="https://msdn.microsoft.com/477FF911-5A17-4EA5-9403-1D7B4E8B3BA5">feature report</a> to a HIDClass device.


## -ioctlparameters




### -input-buffer

A UMDF-based driver calls <a href="https://msdn.microsoft.com/be3f965b-69fe-4d5e-b1b6-3a370603cd7b">IWDFRequest::GetInputMemory</a> to retrieve a  requester-allocated input buffer that contains a feature report.

The driver retrieves the report ID associated with the top-level collection by calling <a href="https://msdn.microsoft.com/96de6f7a-da1d-44a6-b1f7-44859312a662">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter, as shown in the following example.<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UCHAR reportId;
SIZE_T outBufferSize;

FxRequest-&gt;GetDeviceIoControlParameters(NULL, NULL, &amp;outBufferSize);
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

The size of the buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">IWDFRequest::SetInformation</a> to set the number of bytes transferred to the device.</li>
<li>Call <a href="https://msdn.microsoft.com/2fa389f8-8277-4795-a89e-ac5d92004310">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541176">IOCTL_HID_SET_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439657">IOCTL_UMDF_HID_GET_FEATURE</a>
 

 

