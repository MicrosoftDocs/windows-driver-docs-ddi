---
UID: NS:bthioctl._BTH_SDP_CONNECT
title: _BTH_SDP_CONNECT (bthioctl.h)
description: The BTH_SDP_CONNECT structure contains input and output information about a connection between the local Bluetooth system and a remote SDP server. This structure is passed as the input buffer and output buffer of IOCTL_BTH_SDP_CONNECT.
old-location: bltooth\bth_sdp_connect.htm
tech.root: bltooth
ms.assetid: 328dca02-9276-4a3d-acac-e00721863243
ms.date: 04/27/2018
ms.keywords: "*PBTH_SDP_CONNECT, BTH_SDP_CONNECT, BTH_SDP_CONNECT structure [Bluetooth Devices], PBTH_SDP_CONNECT, PBTH_SDP_CONNECT structure pointer [Bluetooth Devices], _BTH_SDP_CONNECT, bltooth.bth_sdp_connect, bth_structs_5502fd7e-54f1-46dd-a441-68103d439c27.xml, bthioctl/BTH_SDP_CONNECT, bthioctl/PBTH_SDP_CONNECT"
f1_keywords:
 - "bthioctl/BTH_SDP_CONNECT"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthioctl.h
api_name:
- BTH_SDP_CONNECT
product:
- Windows
targetos: Windows
req.typenames: BTH_SDP_CONNECT, *PBTH_SDP_CONNECT
---

# _BTH_SDP_CONNECT structure


## -description


The BTH_SDP_CONNECT structure contains input and output information about a connection between the
  local Bluetooth system and a remote SDP server. This structure is passed as the input buffer and output
  buffer of 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a>.


## -struct-fields




### -field bthAddress

The address of the remote SDP server that the local system connects to. This address cannot be to
     the local radio.


### -field fSdpConnect

A flag or combination of flags that determines how to handle the connection request. Valid flag
     values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SDP_CONNECT_ALLOW_PIN

</td>
<td>
If requested, perform a pin exchange with the remote device.

</td>
</tr>
<tr>
<td>
SDP_CONNECT_CACHE

</td>
<td>
Requests are serviced out of the local cache of the SDP record.

</td>
</tr>
</table>
 


### -field HANDLE_SDP_FIELD_NAME

 


### -field requestTimeout

The timeout, in seconds, for requests to the SDP connection handle that is returned in the 
     <b>hConnection</b> member. If the request times out, the SDP connection returned in 
     <b>hConnection</b> must be closed. The values for this field are bound by SDP_REQUEST_TO_MIN and
     SDP_REQUEST_TO_MAX. If SDP_REQUEST_TO_DEFAULT is specified, the timeout is 30 seconds.


#### - hConnection

A handle for the SDP connection on the remote server.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_connect">IOCTL_BTH_SDP_CONNECT</a>
 

 

