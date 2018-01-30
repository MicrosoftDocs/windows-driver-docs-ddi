---
UID: NI:hidport.IOCTL_UMDF_HID_SET_OUTPUT_REPORT
title: IOCTL_UMDF_HID_SET_OUTPUT_REPORT
author: windows-driver-content
description: The IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code sends an output report to a top-level collection.
old-location: hid\ioctl_umdf_hid_set_output_report.htm
old-project: hid
ms.assetid: 9D2BF078-305F-4656-8BA0-F03959209874
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.ioctl_umdf_hid_set_output_report, IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code, IOCTL_UMDF_HID_SET_OUTPUT_REPORT, hidport/IOCTL_UMDF_HID_SET_OUTPUT_REPORT, umdf.ioctl_umdf_hid_set_output_report
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
-	IOCTL_UMDF_HID_SET_OUTPUT_REPORT
product: Windows
targetos: Windows
req.typenames: "*PUSAGE_AND_PAGE, USAGE_AND_PAGE"
---

# IOCTL_UMDF_HID_SET_OUTPUT_REPORT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_UMDF_HID_SET_OUTPUT_REPORT</b> 
   control code sends an <a href="https://msdn.microsoft.com/477FF911-5A17-4EA5-9403-1D7B4E8B3BA5">output report</a> to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.


## -ioctlparameters




### -input-buffer

A UMDF-based driver calls <a href="https://msdn.microsoft.com/be3f965b-69fe-4d5e-b1b6-3a370603cd7b">IWDFRequest::GetInputMemory</a> to retrieve a  requester-allocated input buffer that contains an output report. 


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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

HID minidrivers that carry out the I/O to the device must also:
<ul>
<li>Call <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">IWDFRequest::SetInformation</a> to set the number of bytes transferred to the device.</li>
<li>Call <a href="https://msdn.microsoft.com/2fa389f8-8277-4795-a89e-ac5d92004310">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439661">IOCTL_UMDF_HID_GET_INPUT_REPORT</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\wdf]:%20IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

