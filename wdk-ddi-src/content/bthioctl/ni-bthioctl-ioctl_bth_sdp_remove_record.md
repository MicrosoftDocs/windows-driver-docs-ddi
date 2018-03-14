---
UID: NI:bthioctl.IOCTL_BTH_SDP_REMOVE_RECORD
title: IOCTL_BTH_SDP_REMOVE_RECORD
author: windows-driver-content
description: The IOCTL_BTH_SDP_REMOVE_RECORD request removes a local SDP record that the profile driver previously submitted. The local server will no longer offer this record to remote devices.
old-location: bltooth\ioctl_bth_sdp_remove_record.htm
old-project: bltooth
ms.assetid: 8d559078-ece5-4e15-b010-e39b86679398
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_BTH_SDP_REMOVE_RECORD, IOCTL_BTH_SDP_REMOVE_RECORD control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_remove_record, bth_ioctls_863ca82b-4cb5-444c-bd29-b1d620e509a4.xml, bthioctl/IOCTL_BTH_SDP_REMOVE_RECORD
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
-	IOCTL_BTH_SDP_REMOVE_RECORD
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_SDP_REMOVE_RECORD IOCTL


## -description



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
The remote SDP server is disconnected.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The SDP connection handle passed in the input buffer is invalid.

</td>
</tr>
<tr>
<td>
STATUS_NOT_FOUND

</td>
<td>
The SDP connection handle passed in the input buffer was not found.

</td>
</tr>
</table>
 


## -remarks



If the record to be removed was published using IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO, this indicates
    that class of device (CoD) bits were set. In this case, calling IOCTL_BTH_SDP_REMOVE_RECORD might cause
    the CoD bits to be cleared. The bits will remain set if another client has set them but has not called
    this IOCTL.




## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record.md">IOCTL_BTH_SDP_SUBMIT_RECORD</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
   IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_SDP_REMOVE_RECORD control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

