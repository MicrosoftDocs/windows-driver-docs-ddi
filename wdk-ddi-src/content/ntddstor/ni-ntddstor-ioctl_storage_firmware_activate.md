---
UID: NI:ntddstor.IOCTL_STORAGE_FIRMWARE_ACTIVATE
title: IOCTL_STORAGE_FIRMWARE_ACTIVATE (ntddstor.h)
description: A driver can use IOCTL_STORAGE_FIRMWARE_ACTIVATE to activate a firmware image on a storage device.
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
 - IOCTL_STORAGE_FIRMWARE_ACTIVATE
 - ntddstor/IOCTL_STORAGE_FIRMWARE_ACTIVATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_FIRMWARE_ACTIVATE
---

# IOCTL_STORAGE_FIRMWARE_ACTIVATE IOCTL

## -description

A driver can use **IOCTL_STORAGE_FIRMWARE_ACTIVATE** to activate a firmware image on a storage device.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

**Irp->AssociatedIrp.SystemBuffer** contains [STORAGE_HW_FIRMWARE_ACTIVATE](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate) data that specifies information about the downloaded firmware to activate.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= ```sizeof(STORAGE_HW_FIRMWARE_ACTIVATE)```.

### -output-buffer

This IOCTL has no output structure.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field is set to the number of bytes returned. The **Status** field is set to **STATUS_SUCCESS**, or possibly to **STATUS_INSUFFICIENT_RESOURCES**.

## -see-also

[IOCTL_STORAGE_FIRMWARE_DOWNLOAD](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_download)

[IOCTL_STORAGE_FIRMWARE_GET_INFO](/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_get_info)

[STORAGE_HW_FIRMWARE_ACTIVATE](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate)

[STORAGE_HW_FIRMWARE_DOWNLOAD](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_download)

[STORAGE_HW_FIRMWARE_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info)

[STORAGE_HW_FIRMWARE_INFO_QUERY](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info_query)

[STORAGE_HW_FIRMWARE_SLOT_INFO](/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_slot_info)
