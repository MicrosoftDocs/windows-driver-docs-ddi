---
UID: NI:bthioctl.IOCTL_BTH_SDP_ATTRIBUTE_SEARCH
title: IOCTL_BTH_SDP_ATTRIBUTE_SEARCH
author: windows-driver-content
description: The IOCTL_BTH_SDP_ATTRIBUTE_SEARCH request obtains attributes for the specified SDP record.
old-location: bltooth\ioctl_bth_sdp_attribute_search.htm
tech.root: bltooth
ms.assetid: 30daf70e-34d1-45f7-a69b-503e275b83af
ms.date: 4/27/2018
ms.keywords: IOCTL_BTH_SDP_ATTRIBUTE_SEARCH, IOCTL_BTH_SDP_ATTRIBUTE_SEARCH control, IOCTL_BTH_SDP_ATTRIBUTE_SEARCH control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_attribute_search, bth_ioctls_19f12c1a-aaf5-4751-ba53-94054d3fb725.xml, bthioctl/IOCTL_BTH_SDP_ATTRIBUTE_SEARCH
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthioctl.h
api_name:
-	IOCTL_BTH_SDP_ATTRIBUTE_SEARCH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_ATTRIBUTE_SEARCH IOCTL


## -description



The IOCTL_BTH_SDP_ATTRIBUTE_SEARCH request obtains attributes for the specified SDP record.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="https://msdn.microsoft.com/46198c94-df83-42bb-ad3e-181f252ccd99">
      BTH_SDP_ATTRIBUTE_SEARCH_REQUEST</a> structure that specifies the remote computer range of attributes
      to search plus other key members.


### -input-buffer-length

The length of a 
      <a href="https://msdn.microsoft.com/46198c94-df83-42bb-ad3e-181f252ccd99">
      BTH_SDP_ATTRIBUTE_SEARCH_REQUEST</a> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that contains a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536653">BTH_SDP_STREAM_RESPONSE</a> structure
      that is followed by a variable-length raw SDP stream.


### -output-buffer-length

The length of a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536653">BTH_SDP_STREAM_RESPONSE</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536653">BTH_SDP_STREAM_RESPONSE</a> or the size
      of the output buffer, whichever is smaller. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
The device on which the SDP service resides was not connected.

</td>
</tr>
<tr>
<td>
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
There was not enough memory to complete this operation.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The output buffer was sized incorrectly.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
One of the values in the input buffer was not valid.

</td>
</tr>
<tr>
<td>
STATUS_REQUEST_NOT_ACCEPTED

</td>
<td>
The SDP service rejected the request.

</td>
</tr>
<tr>
<td>
STATUS_TOO_MANY_GUIDS_REQUESTED

</td>
<td>
The SDP service could not process the number of GUIDs passed in the input buffer.

</td>
</tr>
</table>
 


## -remarks



In most circumstances, profile drivers can combine SDP service and attribute searches by calling the 
    <a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
    IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a> IOCTL. If a profile driver must reduce the amount of SDP
    traffic that is transmitted over the Bluetooth link, or extract information from the SDP server by using
    a small number of message transfer units (MTUs), the profile driver should call the 
    <a href="https://msdn.microsoft.com/aea2aff2-5983-4583-9cc8-a45401ecdfb6">
    IOCTL_BTH_SDP_SERVICE_SEARCH</a> IOCTL to perform a service search. The profile driver should then call
    the IOCTL_BTH_SDP_ATTRIBUTE_SEARCH IOCTL to perform an attribute search.

The BTH_SDP_STREAM_RESPONSE structure returned in the output buffer contains information about the
    size of the entire SDP record, the size, in bytes, of the raw SDP record stream that follows the
    BTH_SDP_STREAM_RESPONSE structure, and the first byte of that stream. The variable-length stream is the
    SDP record attributes returned by the search.




## -see-also




<a href="https://msdn.microsoft.com/46198c94-df83-42bb-ad3e-181f252ccd99">
   BTH_SDP_ATTRIBUTE_SEARCH_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536653">BTH_SDP_STREAM_RESPONSE</a>



<a href="https://msdn.microsoft.com/f0955e88-df80-4f53-bc5f-5a38a840aab4">
   IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536692">IOCTL_BTH_SDP_SERVICE_SEARCH</a>
 

 

