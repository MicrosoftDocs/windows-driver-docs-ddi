---
UID: NS:ntddstor._DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
title: _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT (ntddstor.h)
description: The DEVICE_DSM_OUTPUT (or DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT) structure describes output for IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code requests for some data set management actions.
old-location: storage\device_manage_data_set_attributes_output.htm
tech.root: storage
ms.assetid: FFC52136-8A1C-48F6-A846-C1C5BFB4570C
ms.date: 08/23/2019
keywords: ["_DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure"]
ms.keywords: "DEVICE_DSM_OUTPUT, PDEVICE_DSM_OUTPUT, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure [Storage Devices], PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure pointer [Storage Devices], _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, ntddstor/PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, storage.device_manage_data_set_attributes_output"
f1_keywords:
 - "ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
---

# _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure

## -description

The **DEVICE_DSM_OUTPUT** (or DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT) structure describes output for [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes) requests for some data set management actions.

## -struct-fields

### -field Size

Size of this structure, in bytes. Set this member to **sizeof**(DEVICE_DSM_OUTPUT).

### -field Action

DEVICE_DSM_ACTION value that specifies the action related to the instance of this structure. See [DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions) for a list of values and action descriptions.

### -field Flags

Flags for the data set management action. See the **Flags** member of [IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes).

### -field OperationStatus

Status resulting from the operation performed for **Action**.

### -field ExtendedError

An extended error value originating from Windows or a driver.

### -field TargetDetailedError

An error value resulting from a failure execute the operation for **Action** at the target.

### -field ReservedStatus

Reserved.

### -field OutputBlockOffset

The position, after the beginning of this structure, where action-specific data is located.

### -field OutputBlockLength

The length of the action-specific data, in bytes.

## -remarks

Depending on the value of **Action**, an output block is written at an offset of **OutputBlockOffset** after the beginning of this structure. The size of the output block is specified in **OutputBlockLength**.

## -see-also

[DEVICE_DSM_ACTION Descriptions](https://docs.microsoft.com/windows-hardware/drivers/storage/device-dsm-action-descriptions)

[DEVICE_DATA_SET_LB_PROVISIONING_STATE](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_device_data_set_lb_provisioning_state)

[IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes)
