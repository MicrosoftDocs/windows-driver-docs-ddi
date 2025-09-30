---
UID: NI:ntddstor.IOCTL_STORAGE_FIRMWARE_GET_INFO
title: IOCTL_STORAGE_FIRMWARE_GET_INFO (ntddstor.h)
description: A driver can use IOCTL_STORAGE_FIRMWARE_GET_INFO to query a storage device for detailed firmware information.
tech.root: storage
ms.date: 09/29/2025
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_STORAGE_FIRMWARE_GET_INFO
 - ntddstor/IOCTL_STORAGE_FIRMWARE_GET_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_FIRMWARE_GET_INFO
---

# IOCTL_STORAGE_FIRMWARE_GET_INFO IOCTL

## -description

A driver can use **IOCTL_STORAGE_FIRMWARE_GET_INFO** to query a storage device for detailed firmware information. A successful call will return information about firmware revisions, activity status, as well as read/write attributes for each slot. The amount of data returned varies based on storage protocol.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

**Irp->AssociatedIrp.SystemBuffer** contains [STORAGE_HW_FIRMWARE_INFO_QUERY](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info_query) data that specifies the target of the request.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= ```sizeof(STORAGE_HW_FIRMWARE_INFO_QUERY)```.

### -output-buffer

The driver returns query data to the buffer at **Irp->AssociatedIrp.SystemBuffer**. The output buffer should contain a [STORAGE_HW_FIRMWARE_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info) and [STORAGE_HW_FIRMWARE_SLOT_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_slot_info) structure for each slot on the device.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** indicates the number of bytes that can be written to **Irp->AssociatedIrp.SystemBuffer**. **OutputBufferLength** must be **sizeof**([STORAGE_HW_FIRMWARE_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info)) + ```sizeof(STORAGE_HW_FIRMWARE_SLOT_INFO) * (STORAGE_HW_FIRMWARE_INFO.SlotCount -1)```.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field is set to the number of bytes returned. The **Status** field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED.

## -see-also

[IOCTL_STORAGE_FIRMWARE_ACTIVATE](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_activate)

[IOCTL_STORAGE_FIRMWARE_DOWNLOAD](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_download)

[STORAGE_HW_FIRMWARE_ACTIVATE](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate)

[STORAGE_HW_FIRMWARE_DOWNLOAD](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_download)

[STORAGE_HW_FIRMWARE_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info)

[STORAGE_HW_FIRMWARE_INFO_QUERY](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info_query)

[STORAGE_HW_FIRMWARE_SLOT_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_slot_info)
