---
UID: NI:ntddstor.IOCTL_STORAGE_FIRMWARE_ACTIVATE
title: IOCTL_STORAGE_FIRMWARE_ACTIVATE (ntddstor.h)
description: A driver can use IOCTL_STORAGE_FIRMWARE_ACTIVATE to activate a firmware image on a storage device.
old-location: storage\ioctl_storage_firmware_activate.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_FIRMWARE_ACTIVATE IOCTL"]
ms.keywords: IOCTL_STORAGE_FIRMWARE_ACTIVATE, IOCTL_STORAGE_FIRMWARE_ACTIVATE control, IOCTL_STORAGE_FIRMWARE_ACTIVATE control code [Storage Devices], ntddstor/IOCTL_STORAGE_FIRMWARE_ACTIVATE, storage.ioctl_storage_firmware_activate
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

A driver can use <b>IOCTL_STORAGE_FIRMWARE_ACTIVATE</b> to activate a firmware image on a storage device.

## -ioctlparameters

### -input-buffer

<b>
       Irp->AssociatedIrp.SystemBuffer</b> contains <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate">STORAGE_HW_FIRMWARE_ACTIVATE</a> data that specifies information about the downloaded firmware to activate.

### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be >= <b>sizeof</b>(<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate">STORAGE_HW_FIRMWARE_ACTIVATE</a>).

### -output-buffer

This IOCTL has no output structure.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_download">IOCTL_STORAGE_FIRMWARE_DOWNLOAD</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_firmware_get_info">IOCTL_STORAGE_FIRMWARE_GET_INFO</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_activate">STORAGE_HW_FIRMWARE_ACTIVATE</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_download">STORAGE_HW_FIRMWARE_DOWNLOAD</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info">STORAGE_HW_FIRMWARE_INFO</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_info_query">STORAGE_HW_FIRMWARE_INFO_QUERY</a>



<a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_hw_firmware_slot_info">STORAGE_HW_FIRMWARE_SLOT_INFO</a>
