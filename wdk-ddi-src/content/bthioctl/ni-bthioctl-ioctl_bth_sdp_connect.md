---
UID: NI:bthioctl.IOCTL_BTH_SDP_CONNECT
title: IOCTL_BTH_SDP_CONNECT
author: windows-driver-content
description: The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth device.
old-location: bltooth\ioctl_bth_sdp_connect.htm
old-project: bltooth
ms.assetid: 8bfe92c9-6049-4d68-80a9-3a8f8dda3bcc
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.ioctl_bth_sdp_connect, IOCTL_BTH_SDP_CONNECT control code [Bluetooth Devices], IOCTL_BTH_SDP_CONNECT, bthioctl/IOCTL_BTH_SDP_CONNECT, bth_ioctls_e03c93b3-b2af-40d0-a296-bb76f33c38a2.xml
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
-	IOCTL_BTH_SDP_CONNECT
product: Windows
targetos: Windows
req.typenames: "*PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1"
---

# IOCTL_BTH_SDP_CONNECT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth
     device.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_connect.md">BTH_SDP_CONNECT</a> structure that specifies
      the address of the remote SDP server, the request's timeout setting, and other information specific to
      the connection.


### -input-buffer-length

Length of a <a href="..\bthioctl\ns-bthioctl-_bth_sdp_connect.md">BTH_SDP_CONNECT</a> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a BTH_SDP_CONNECT structure that holds the SDP
      connection handle to the remote server.


### -output-buffer-length

Length of a <a href="..\bthioctl\ns-bthioctl-_bth_sdp_connect.md">BTH_SDP_CONNECT</a> structure.


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
STATUS_DEVICE_BUSY

</td>
<td>
The HCI layer is currently unable to accept requests.

</td>
</tr>
<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
If a cached connection was specified, there are no cached records available. Otherwise, the
         connection was canceled before it completed.

</td>
</tr>
<tr>
<td>
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
There was not enough memory available to process the request.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
A portion of the structure found in the input buffer was incorrect.

</td>
</tr>
<tr>
<td>
STATUS_PENDING

</td>
<td>
The system cannot currently respond, but will attempt to shortly.

</td>
</tr>
</table> 


## -remarks


The IOCTL_BTH_SDP_CONNECT request allows a profile driver to obtain an SDP connection handle to a
    remote device. After the SDP connection handle is obtained, the profile driver can pass it to other SDP
    IOCTL interfaces to gather information about the remote device's SDP server. When the SDP queries are
    completed, the profile driver must close the SDP connection with 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_disconnect.md">IOCTL_BTH_SDP_DISCONNECT</a>.



## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_disconnect.md">IOCTL_BTH_SDP_DISCONNECT</a>

<a href="..\bthioctl\ns-bthioctl-_bth_sdp_connect.md">BTH_SDP_CONNECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_CONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

