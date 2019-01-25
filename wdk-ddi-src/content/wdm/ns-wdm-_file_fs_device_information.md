---
UID: NS:wdm._FILE_FS_DEVICE_INFORMATION
title: "_FILE_FS_DEVICE_INFORMATION" (wdm.h)
description: The FILE_FS_DEVICE_INFORMATION structure provides file system device information about the type of device object associated with a file object.
old-location: kernel\file_fs_device_information.htm
tech.root: kernel
ms.assetid: 0849bbc2-cfc7-4437-896d-3f46e8f6461a
ms.date: 04/30/2018
ms.keywords: "*PFILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_FS_DEVICE_INFORMATION, PFILE_FS_DEVICE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_FS_DEVICE_INFORMATION, kernel.file_fs_device_information, kstruct_b_86acb464-7e57-467f-998e-896b0a7cebc4.xml, wdm/FILE_FS_DEVICE_INFORMATION, wdm/PFILE_FS_DEVICE_INFORMATION"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	FILE_FS_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_FS_DEVICE_INFORMATION, *PFILE_FS_DEVICE_INFORMATION
---

# _FILE_FS_DEVICE_INFORMATION structure


## -description


The <b>FILE_FS_DEVICE_INFORMATION</b> structure provides file system device information about the type of device object associated with a file object.


## -struct-fields




### -field DeviceType

Set when a driver calls <b>IoCreateDevice</b> as appropriate for the type of underlying device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.


### -field Characteristics

The device characteristics. For a description of relevant values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
 

 

