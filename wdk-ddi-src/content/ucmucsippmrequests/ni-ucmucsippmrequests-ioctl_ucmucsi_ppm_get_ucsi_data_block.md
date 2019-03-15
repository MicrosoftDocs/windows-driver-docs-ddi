---
UID: NI:ucmucsippmrequests.IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK
title: IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK (ucmucsippmrequests.h)
tech.root: usbref
description: 
ms.assetid: 8572406b-0348-4b9b-bd82-6f3d88b733ed
ms.date: 09/30/2018
ms.topic: ioctl
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ucmucsippmrequests.h
api_name: 
- IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# IOCTL_UCMUCSI_PPM_GET_UCSI_DATA_BLOCK IOCTL

### Major Code:  [IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description
Gets a UCSI data block from the PPM firmware by using the supported transport.


## -ioctlparameters

### -input-buffer

A pointer a [**UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS**](ns-ucmucsippmrequests-_ucmucsi_ppm_get_ucsi_data_block_in_params.md) structure that contains the PPM object that managers the PPM hardware.

### -input-buffer-length 

Size of the **UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_IN_PARAMS** structure.

### -output-buffer

A pointer a [**UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS**](ns-ucmucsippmrequests-_ucmucsi_ppm_get_ucsi_data_block_out_params.md) structure that contains the PPM object that managers the PPM hardware.

### -output-buffer-length

Size of the **UCMUCSI_PPM_GET_UCSI_DATA_BLOCK_OUT_PARAMS** structure.

### -in-out-buffer


### -inout-buffer-length



### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, set to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Certain UCSI commands do not generate notifications from the PPM firmware, such as the PPM_RESET command. When this command is received, the firmware disables all notification. The UcmUcsiCx class extension sends such commands to the client driver through this IOCTL request. The client driver is expected to poll on reset complete indicator and return the current result from the firmware to UcmUcsiCx.  

## -see-also
