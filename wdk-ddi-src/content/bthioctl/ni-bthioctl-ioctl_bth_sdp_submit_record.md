---
UID: NI:bthioctl.IOCTL_BTH_SDP_SUBMIT_RECORD
title: IOCTL_BTH_SDP_SUBMIT_RECORD
author: windows-driver-content
description: The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP server, allowing the client to advertise that a service is available on the local computer.
old-location: bltooth\ioctl_bth_sdp_submit_record.htm
old-project: bltooth
ms.assetid: ec6739d3-5956-4cc2-90ff-75c67c0a84e7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_BTH_SDP_SUBMIT_RECORD, IOCTL_BTH_SDP_SUBMIT_RECORD control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_submit_record, bth_ioctls_e32ecb99-7a41-4405-844e-8c1038d3cb89.xml, bthioctl/IOCTL_BTH_SDP_SUBMIT_RECORD
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
-	IOCTL_BTH_SDP_SUBMIT_RECORD
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_SDP_SUBMIT_RECORD IOCTL


## -description



The IOCTL_BTH_SDP_SUBMIT_RECORD request allows a profile driver to add an SDP record to the local SDP
     server, allowing the client to advertise that a service is available on the local computer. The profile
     driver calls 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536690">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
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

If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the handle that
      the IOCTL returns. Otherwise, the 
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
STATUS_INSUFFICIENT_RESOURCES

</td>
<td>
Not enough memory was allocated to process this request.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The output buffer was sized incorrectly.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_PARAMETER

</td>
<td>
The stream passed to the input buffer was invalid.

</td>
</tr>
</table>
 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536690">IOCTL_BTH_SDP_REMOVE_RECORD</a>
 

 

