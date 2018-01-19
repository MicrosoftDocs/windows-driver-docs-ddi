---
UID: NI:bthioctl.IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
title: IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
author: windows-driver-content
description: The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along with attributes that are not part of the SDP record itself.
old-location: bltooth\ioctl_bth_sdp_submit_record_with_info.htm
old-project: bltooth
ms.assetid: 774d1bda-2d9b-4ab4-97cf-b358471d8716
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
req.alt-api: IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
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

# IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO IOCTL



## -description

The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along
     with attributes that are not part of the SDP record itself. After this call completes successfully, the
     profile driver can advertise that a service is available on the local computer. The profile driver calls
     
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
     stop advertising the service on the local SDP server.



The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along
     with attributes that are not part of the SDP record itself. After this call completes successfully, the
     profile driver can advertise that a service is available on the local computer. The profile driver calls
     
     <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_remove_record.md">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
     stop advertising the service on the local SDP server.



## -ioctlparameters

### -input-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_record.md">BTH_SDP_RECORD</a> structure that specifies the
      SDP record to add, its size, the required security for the record, and publication options for the
      record. The structure is followed by the raw SDP record.


### -input-buffer-length
The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_sdp_record.md">BTH_SDP_RECORD</a> structure.


### -output-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a handle to the SDP record. This
      handle can only be used by IOCTL_BTH_SDP_REMOVE_RECORD to remove the record submitted by
      IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO.


### -output-buffer-length
The length of the handle to the SDP record.


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

A member of the structure passed to the input buffer, or the stream passed to the input buffer,
         was invalid.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record.md">IOCTL_BTH_SDP_SUBMIT_RECORD</a>
</dt>
<dt>
<a href="..\bthioctl\ns-bthioctl-_bth_sdp_record.md">BTH_SDP_RECORD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

