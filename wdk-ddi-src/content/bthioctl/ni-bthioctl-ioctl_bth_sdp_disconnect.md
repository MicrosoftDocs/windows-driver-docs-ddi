---
UID: NI:bthioctl.IOCTL_BTH_SDP_DISCONNECT
title: IOCTL_BTH_SDP_DISCONNECT (bthioctl.h)
description: The IOCTL_BTH_SDP_DISCONNECT request closes a connection to a remote SDP server.
old-location: bltooth\ioctl_bth_sdp_disconnect.htm
tech.root: bltooth
ms.assetid: 1d45465c-21ee-423c-967a-4462b61c2f0e
ms.date: 04/27/2018
ms.keywords: IOCTL_BTH_SDP_DISCONNECT, IOCTL_BTH_SDP_DISCONNECT control, IOCTL_BTH_SDP_DISCONNECT control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_disconnect, bth_ioctls_6cff5fc3-aff6-4e9b-8192-c6cd7c8f5fea.xml, bthioctl/IOCTL_BTH_SDP_DISCONNECT
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_BTH_SDP_DISCONNECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_DISCONNECT IOCTL


## -description



The IOCTL_BTH_SDP_DISCONNECT request closes a connection to a remote SDP server.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains an 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536649">BTH_SDP_DISCONNECT</a> structure that
      specifies the connection handle to the remote SDP connection to terminate.


### -input-buffer-length

Length of an 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff536649">BTH_SDP_DISCONNECT</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a> must issue an
    IOCTL_BTH_SDP_DISCONNECT IOCTL when the SDP connection is no longer needed. After
    IOCTL_BTH_SDP_DISCONNECT is called, the specified SDP handle is no longer valid.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536649">BTH_SDP_DISCONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536688">IOCTL_BTH_SDP_CONNECT</a>
 

 

