---
UID: NI:bthioctl.IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH
title: IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH (bthioctl.h)
description: The IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH request combines an SDP service and attribute search into a single operation. This allows a caller to directly obtain SDP records from a remote device.
old-location: bltooth\ioctl_bth_sdp_service_attribute_search.htm
tech.root: bltooth
ms.assetid: f0955e88-df80-4f53-bc5f-5a38a840aab4
ms.date: 04/27/2018
ms.keywords: IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH, IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH control, IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_service_attribute_search, bth_ioctls_73db8572-0986-4ac7-a76c-4cb3777c0660.xml, bthioctl/IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH
ms.topic: ioctl
f1_keywords:
 - "bthioctl/IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH"
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH IOCTL


## -description



The IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH request combines an SDP service and attribute search into
     a single operation. This allows a caller to directly obtain SDP records from a remote device.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains an 
      <b>
      IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</b> structure that specifies the connection handle to the
      remote SDP server, an array of GUIDs, and the range of attribute values to search for.


### -input-buffer-length

The length of an 
      <b>
      IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</b> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_stream_response">BTH_SDP_STREAM_RESPONSE</a> structure
      followed by a raw SDP record stream.


### -output-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_stream_response">BTH_SDP_STREAM_RESPONSE</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the SDP
      response stream or the size of the output buffer, whichever is smaller. Otherwise, the 
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



After a profile driver obtains an SDP record, it can use SDP functions to parse them. Pointers to
    these functions are provided by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">
    BTHDDI_SDP_PARSE_INTERFACE</a> interface.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_stream_response">BTH_SDP_STREAM_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_service_attribute_search">
   IOCTL_BTH_SDP_SERVICE_ATTRIBUTE_SEARCH</a>
 

 

