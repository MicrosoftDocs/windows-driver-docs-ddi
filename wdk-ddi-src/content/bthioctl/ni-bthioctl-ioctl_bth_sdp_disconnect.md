---
UID: NI:bthioctl.IOCTL_BTH_SDP_DISCONNECT
title: IOCTL_BTH_SDP_DISCONNECT
author: windows-driver-content
description: The IOCTL_BTH_SDP_DISCONNECT request closes a connection to a remote SDP server.
old-location: bltooth\ioctl_bth_sdp_disconnect.htm
old-project: bltooth
ms.assetid: 1d45465c-21ee-423c-967a-4462b61c2f0e
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.ioctl_bth_sdp_disconnect, IOCTL_BTH_SDP_DISCONNECT control code [Bluetooth Devices], IOCTL_BTH_SDP_DISCONNECT, bthioctl/IOCTL_BTH_SDP_DISCONNECT, bth_ioctls_6cff5fc3-aff6-4e9b-8192-c6cd7c8f5fea.xml
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
-	IOCTL_BTH_SDP_DISCONNECT
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_SDP_DISCONNECT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_BTH_SDP_DISCONNECT request closes a connection to a remote SDP server.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains an 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_disconnect.md">BTH_SDP_DISCONNECT</a> structure that
      specifies the connection handle to the remote SDP connection to terminate.


### -input-buffer-length

Length of an 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_disconnect.md">BTH_SDP_DISCONNECT</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero.

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
The specified SDP server has already been disconnected.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The connection handle passed in the input buffer is invalid.

</td>
</tr>
</table> 


## -remarks


Callers of 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a> must issue an
    IOCTL_BTH_SDP_DISCONNECT IOCTL when the SDP connection is no longer needed. After
    IOCTL_BTH_SDP_DISCONNECT is called, the specified SDP handle is no longer valid.



## -see-also

<a href="..\bthioctl\ns-bthioctl-_bth_sdp_disconnect.md">BTH_SDP_DISCONNECT</a>

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_DISCONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

