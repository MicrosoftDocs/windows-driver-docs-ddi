---
UID: NI:ucmucsippmrequests.IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK
title: IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK (ucmucsippmrequests.h)
tech.root: usbref
description: Sends a UCSI data block to the client driver.
ms.date: 09/30/2018
keywords: ["IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK IOCTL"]
req.header: Ucmucsippmrequests.h
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK
 - ucmucsippmrequests/IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ucmucsippmrequests.h
api_name:
 - IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK
---

# IOCTL_UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

Sends a UCSI data block to the PPM firmware by using the supported transport.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

A pointer to a [**UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS**](ns-ucmucsippmrequests-_ucmucsi_ppm_send_ucsi_data_block_in_params.md) structure that contains the UCSI data block.

### -input-buffer-length 

Size of the **UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS** structure.

### -output-buffer

### -output-buffer-length 

### -in-out-buffer

### -inout-buffer-length 

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, set to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Whenever the UcmUcsiCx class extension asynchronously needs to send a UCSI block to the PPM firmware, the class extension sends this IOCTL request to the client driver asynchronously.

## -see-also

[**UCMUCSI_PPM_SEND_UCSI_DATA_BLOCK_IN_PARAMS**](ns-ucmucsippmrequests-_ucmucsi_ppm_send_ucsi_data_block_in_params.md)
