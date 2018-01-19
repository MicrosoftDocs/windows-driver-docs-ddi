---
UID: NI:bthioctl.IOCTL_BTH_SDP_REMOVE_RECORD
title: IOCTL_BTH_SDP_REMOVE_RECORD
author: windows-driver-content
description: The IOCTL_BTH_SDP_REMOVE_RECORD request removes a local SDP record that the profile driver previously submitted. The local server will no longer offer this record to remote devices.
old-location: bltooth\ioctl_bth_sdp_remove_record.htm
old-project: bltooth
ms.assetid: 8d559078-ece5-4e15-b010-e39b86679398
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
req.alt-api: IOCTL_BTH_SDP_REMOVE_RECORD
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

# IOCTL_BTH_SDP_REMOVE_RECORD IOCTL



## -description

The IOCTL_BTH_SDP_REMOVE_RECORD request removes a local SDP record that the profile driver previously
     submitted. The local server will no longer offer this record to remote devices.



The IOCTL_BTH_SDP_REMOVE_RECORD request removes a local SDP record that the profile driver previously
     submitted. The local server will no longer offer this record to remote devices.



## -ioctlparameters

### -input-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member contains an SDP connection handle from which to remove the SDP
      record. This must be a handle returned from a call to 
      <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record.md">IOCTL_BTH_SDP_SUBMIT_RECORD</a> or 
      <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
      IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>. Handles from other sources are invalid in this
      context.


### -input-buffer-length
The length of the buffer.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_DEVICE_NOT_CONNECTED

The remote SDP server is disconnected.

STATUS_INVALID_PARAMETER

The SDP connection handle passed in the input buffer is invalid.

STATUS_NOT_FOUND

The SDP connection handle passed in the input buffer was not found.

 


## -remarks
If the record to be removed was published using IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO, this indicates
    that class of device (CoD) bits were set. In this case, calling IOCTL_BTH_SDP_REMOVE_RECORD might cause
    the CoD bits to be cleared. The bits will remain set if another client has set them but has not called
    this IOCTL.


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record.md">IOCTL_BTH_SDP_SUBMIT_RECORD</a>
</dt>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
   IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_REMOVE_RECORD control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

