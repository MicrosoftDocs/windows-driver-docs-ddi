---
UID: NS:wdm._FILE_FS_DEVICE_INFORMATION
title: _FILE_FS_DEVICE_INFORMATION (wdm.h)
description: The FILE_FS_DEVICE_INFORMATION structure provides file system device information about the type of device object associated with a file object.
old-location: kernel\file_fs_device_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["FILE_FS_DEVICE_INFORMATION structure"]
ms.keywords: "*PFILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_FS_DEVICE_INFORMATION, PFILE_FS_DEVICE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_FS_DEVICE_INFORMATION, kernel.file_fs_device_information, kstruct_b_86acb464-7e57-467f-998e-896b0a7cebc4.xml, wdm/FILE_FS_DEVICE_INFORMATION, wdm/PFILE_FS_DEVICE_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: FILE_FS_DEVICE_INFORMATION, *PFILE_FS_DEVICE_INFORMATION
f1_keywords:
 - _FILE_FS_DEVICE_INFORMATION
 - wdm/_FILE_FS_DEVICE_INFORMATION
 - PFILE_FS_DEVICE_INFORMATION
 - wdm/PFILE_FS_DEVICE_INFORMATION
 - FILE_FS_DEVICE_INFORMATION
 - wdm/FILE_FS_DEVICE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FILE_FS_DEVICE_INFORMATION
 - PFILE_FS_DEVICE_INFORMATION
 - FILE_FS_DEVICE_INFORMATION
---

# _FILE_FS_DEVICE_INFORMATION structure


## -description

The <b>FILE_FS_DEVICE_INFORMATION</b> structure provides file system device information about the type of device object associated with a file object.

## -struct-fields

### -field DeviceType

Set when a driver calls <b>IoCreateDevice</b> as appropriate for the type of underlying device. For more information, see <a href="/windows-hardware/drivers/kernel/specifying-device-types">Specifying Device Types</a>.

### -field Characteristics

The device characteristics. For a description of relevant values, see <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>

