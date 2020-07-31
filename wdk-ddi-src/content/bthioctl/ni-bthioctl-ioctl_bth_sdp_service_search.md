---
UID: NI:bthioctl.IOCTL_BTH_SDP_SERVICE_SEARCH
title: IOCTL_BTH_SDP_SERVICE_SEARCH (bthioctl.h)
description: The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to SDP records of a particular service class or classes.
old-location: bltooth\ioctl_bth_sdp_service_search.htm
tech.root: bltooth
ms.assetid: aea2aff2-5983-4583-9cc8-a45401ecdfb6
ms.date: 04/27/2018
keywords: ["IOCTL_BTH_SDP_SERVICE_SEARCH IOCTL"]
ms.keywords: IOCTL_BTH_SDP_SERVICE_SEARCH, IOCTL_BTH_SDP_SERVICE_SEARCH control, IOCTL_BTH_SDP_SERVICE_SEARCH control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_service_search, bth_ioctls_63b14ae9-91a6-42c7-bdd2-6ab9326f106c.xml, bthioctl/IOCTL_BTH_SDP_SERVICE_SEARCH
f1_keywords:
 - "bthioctl/IOCTL_BTH_SDP_SERVICE_SEARCH"
 - "IOCTL_BTH_SDP_SERVICE_SEARCH"
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
- IOCTL_BTH_SDP_SERVICE_SEARCH
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_SERVICE_SEARCH IOCTL


## -description



The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to
     SDP records of a particular service class or classes.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_service_search_request">
      BTH_SDP_SERVICE_SEARCH_REQUEST</a> structure that specifies the connection handle to the remote SDP
      server and an array of GUIDs to search for.


### -input-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_service_search_request">
      BTH_SDP_SERVICE_SEARCH_REQUEST</a> structure/


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that contains a variable length array of
      unsigned long integer values. Each value represents a remote SDP service record. 


### -output-buffer-length

Callers can determine
      the length of this array by dividing the 
      <b>Information</b> member of the STATUS_BLOCK structure by 
      <code>sizeof(ULONG)</code>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of values in the following table.

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
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_service_search_request">BTH_SDP_SERVICE_SEARCH_REQUEST</a>
 

 

