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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
 - bthioctl/IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthioctl.h
api_name:
 - IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO
---

# IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO IOCTL


## -description

The IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO request adds an SDP record to the local SDP server along with attributes that are not part of the SDP record itself. After this call completes successfully, the profile driver can advertise that a service is available on the local computer. The profile driver calls [IOCTL_BTH_SDP_REMOVE_RECORD](ni-bthioctl-ioctl_bth_sdp_remove_record.md) to stop advertising the service on the local SDP server.

## -ioctlparameters

### -input-buffer

The **AssociatedIrp.SystemBuffer** member contains a [BTH_SDP_RECORD](ns-bthioctl-_bth_sdp_record.md) structure that specifies the SDP record to add, its size, the required security for the record, and publication options for the record. The structure is followed by the raw SDP record.

### -input-buffer-length

The length of a [BTH_SDP_RECORD](ns-bthioctl-_bth_sdp_record.md) structure.

### -output-buffer

The **AssociatedIrp.SystemBuffer** member points to a buffer that holds a handle to the SDP record. This handle can only be used by IOCTL_BTH_SDP_REMOVE_RECORD to remove the record submitted by IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO.

### -output-buffer-length

The length of the handle to the SDP record.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the **Information** member of the STATUS_BLOCK structure is set to the size, in bytes, of the handle that the IOCTL returns. Otherwise, the **Information** member is set to zero.

The **Status** member is set to one of the values in the following table:

| Status value | Description |
| --- | --- |
| STATUS_SUCCESS | The IOCTL completed successfully. |
| STATUS_INSUFFICIENT_RESOURCES | Not enough memory was allocated to process this request. |
| STATUS_INVALID_BUFFER_SIZE | The output buffer was sized incorrectly. |
| STATUS_INVALID_PARAMETER | A member of the structure passed to the input buffer, or the stream passed to the input buffer, was invalid. |

## -see-also

[BTH_SDP_RECORD](ns-bthioctl-_bth_sdp_record.md)

[IOCTL_BTH_SDP_SUBMIT_RECORD](ni-bthioctl-ioctl_bth_sdp_submit_record.md)
