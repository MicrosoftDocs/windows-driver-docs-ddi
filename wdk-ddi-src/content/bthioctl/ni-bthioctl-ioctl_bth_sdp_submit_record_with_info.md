---
UID: NI:bthioctl.IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
title: IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO (bthioctl.h)
description: The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along with attributes that are not part of the SDP record itself.
old-location: bltooth\ioctl_bth_sdp_submit_record_with_info.htm
tech.root: bltooth
ms.assetid: 774d1bda-2d9b-4ab4-97cf-b358471d8716
ms.date: 04/27/2018
keywords: ["IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO IOCTL"]
ms.keywords: IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO, IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO control, IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO control code [Bluetooth Devices], bltooth.ioctl_bth_sdp_submit_record_with_info, bth_ioctls_6ae2aeb0-ecf1-40c4-9135-2397c40a278e.xml, bthioctl/IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
f1_keywords:
 - "bthioctl/IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO"
 - "IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO"
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthioctl.h
api_name:
- IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO IOCTL


## -description



The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along
     with attributes that are not part of the SDP record itself. After this call completes successfully, the
     profile driver can advertise that a service is available on the local computer. The profile driver calls
     
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_remove_record">IOCTL_BTH_SDP_REMOVE_RECORD</a> to
     stop advertising the service on the local SDP server.




## -ioctlparameters




### -input-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member contains a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_record">BTH_SDP_RECORD</a> structure that specifies the
      SDP record to add, its size, the required security for the record, and publication options for the
      record. The structure is followed by the raw SDP record.


### -input-buffer-length

The length of a 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_record">BTH_SDP_RECORD</a> structure.


### -output-buffer

The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a handle to the SDP record. This
      handle can only be used by IOCTL_BTH_SDP_REMOVE_RECORD to remove the record submitted by
      IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO.


### -output-buffer-length

The length of the handle to the SDP record.


### -in-out-buffer








### -inout-buffer-length








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
A member of the structure passed to the input buffer, or the stream passed to the input buffer,
         was invalid.

</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_sdp_record">BTH_SDP_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_sdp_submit_record">IOCTL_BTH_SDP_SUBMIT_RECORD</a>
 

 

