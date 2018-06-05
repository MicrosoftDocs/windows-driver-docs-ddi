---
UID: NI:bthioctl.IOCTL_BTH_SDP_CONNECT
title: IOCTL_BTH_SDP_CONNECT
author: windows-driver-content
description: The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth device.
old-location: bltooth\ioctl_bth_sdp_connect.htm
old-project: bltooth
ms.assetid: 8bfe92c9-6049-4d68-80a9-3a8f8dda3bcc
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: IOCTL_BTH_SDP_CONNECT, IOCTL_BTH_SDP_CONNECT control, IOCTL_BTH_SDP_CONNECT control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_connect, bth_ioctls_e03c93b3-b2af-40d0-a296-bb76f33c38a2.xml, bthioctl/IOCTL_BTH_SDP_CONNECT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthioctl.h
api_name:
-	IOCTL_BTH_SDP_CONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_CONNECT IOCTL


## -description



The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth
     device.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a> structure that specifies
      the address of the remote SDP server, the request's timeout setting, and other information specific to
      the connection.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a BTH_SDP_CONNECT structure that holds the SDP
      connection handle to the remote server.


### -output-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a> structure.


### -in-out-buffer








### -inout-buffer-length








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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536689">IOCTL_BTH_SDP_DISCONNECT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536648">BTH_SDP_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536689">IOCTL_BTH_SDP_DISCONNECT</a>
 

 

