---
UID: NI:bthioctl.IOCTL_BTH_SDP_SERVICE_SEARCH
title: IOCTL_BTH_SDP_SERVICE_SEARCH
author: windows-driver-content
description: The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to SDP records of a particular service class or classes.
old-location: bltooth\ioctl_bth_sdp_service_search.htm
old-project: bltooth
ms.assetid: aea2aff2-5983-4583-9cc8-a45401ecdfb6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.ioctl_bth_sdp_service_search, IOCTL_BTH_SDP_SERVICE_SEARCH control code [Bluetooth Devices], IOCTL_BTH_SDP_SERVICE_SEARCH, bthioctl/IOCTL_BTH_SDP_SERVICE_SEARCH, bth_ioctls_63b14ae9-91a6-42c7-bdd2-6ab9326f106c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthioctl.h
apiname:
-	IOCTL_BTH_SDP_SERVICE_SEARCH
product: Windows
targetos: Windows
req.typenames: "*PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1"
---

# IOCTL_BTH_SDP_SERVICE_SEARCH IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_BTH_SDP_SERVICE_SEARCH request contacts a remote device with an SDP request for handles to
     SDP records of a particular service class or classes.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">
      BTH_SDP_SERVICE_SEARCH_REQUEST</a> structure that specifies the connection handle to the remote SDP
      server and an array of GUIDs to search for.


### -input-buffer-length

The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">
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



<text></text>




### -inout-buffer-length



<text></text>




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

<a href="..\bthioctl\ns-bthioctl-_bth_sdp_service_search_request.md">BTH_SDP_SERVICE_SEARCH_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_SERVICE_SEARCH control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

