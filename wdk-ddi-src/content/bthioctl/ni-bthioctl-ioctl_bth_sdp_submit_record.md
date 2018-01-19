---
UID: NI:bthioctl.IOCTL_BTH_SDP_SUBMIT_RECORD
title: IOCTL_BTH_SDP_SUBMIT_RECORD
author: windows-driver-content
description: The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP server, allowing the client to advertise that a service is available on the local computer.
old-location: bltooth\ioctl_bth_sdp_submit_record.htm
old-project: bltooth
ms.assetid: ec6739d3-5956-4cc2-90ff-75c67c0a84e7
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
req.alt-api: IOCTL_BTH_SDP_SUBMIT_RECORD
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

# IOCTL_BTH_SDP_SUBMIT_RECORD IOCTL



## -description

The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP
     server, allowing the client to advertise that a service is available on the local computer. The profile
     driver calls 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
     stop advertising the server on the local SDP server.



The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP
     server, allowing the client to advertise that a service is available on the local computer. The profile
     driver calls 
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
     stop advertising the server on the local SDP server.



## -ioctlparameters

### -input-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member specifies the raw SDP stream that contains the record to
      advertise.


### -input-buffer-length
The length of the stream.


### -output-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a handle to the SDP record. This
      handle can only be used by IOCTL_BTH_SDP_REMOVE_RECORD to remove the record submitted by
      IOCTL_BTH_SDP_SUBMIT_RECORD.


### -output-buffer-length
The length of the buffer.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the handle that
      the IOCTL returns. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_INSUFFICIENT_RESOURCES

Not enough memory was allocated to process this request.

STATUS_INVALID_BUFFER_SIZE

The output buffer was sized incorrectly.

STATUS_INVALID_PARAMETER

The stream passed to the input buffer was invalid.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md">IOCTL_BTH_SDP_REMOVE_RECORD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_SUBMIT_RECORD control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

