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
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTH_SDP_CONNECT
req.alt-loc: Bthioctl.h
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
req.typenames: *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_SDP_CONNECT IOCTL



## -description

The IOCTL_BTH_SDP_CONNECT request creates a connection to the SDP service on a remote Bluetooth
     device.



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
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_DEVICE_BUSY

The HCI layer is currently unable to accept requests.

STATUS_DEVICE_NOT_CONNECTED

If a cached connection was specified, there are no cached records available. Otherwise, the
         connection was canceled before it completed.

STATUS_INSUFFICIENT_RESOURCES

There was not enough memory available to process the request.

STATUS_INVALID_PARAMETER

A portion of the structure found in the input buffer was incorrect.

STATUS_PENDING

The system cannot currently respond, but will attempt to shortly.

 


## -remarks
The IOCTL_BTH_SDP_CONNECT request allows a profile driver to obtain an SDP connection handle to a
    remote device. After the SDP connection handle is obtained, the profile driver can pass it to other SDP
    IOCTL interfaces to gather information about the remote device's SDP server. When the SDP queries are
    completed, the profile driver must close the SDP connection with 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_disconnect.md">IOCTL_BTH_SDP_DISCONNECT</a>.


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_sdp_connect.md">BTH_SDP_CONNECT</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_disconnect.md">IOCTL_BTH_SDP_DISCONNECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_CONNECT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

