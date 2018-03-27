---
UID: NS:wdm._FILE_FS_DEVICE_INFORMATION
title: "_FILE_FS_DEVICE_INFORMATION"
author: windows-driver-content
description: The FILE_FS_DEVICE_INFORMATION structure provides file system device information about the type of device object associated with a file object.
old-location: kernel\file_fs_device_information.htm
old-project: kernel
ms.assetid: 0849bbc2-cfc7-4437-896d-3f46e8f6461a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PFILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION, FILE_FS_DEVICE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_FS_DEVICE_INFORMATION, PFILE_FS_DEVICE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_FS_DEVICE_INFORMATION, kernel.file_fs_device_information, kstruct_b_86acb464-7e57-467f-998e-896b0a7cebc4.xml, wdm/FILE_FS_DEVICE_INFORMATION, wdm/PFILE_FS_DEVICE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	FILE_FS_DEVICE_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_DEVICE_INFORMATION, *PFILE_FS_DEVICE_INFORMATION
req.product: Windows 10 or later.
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_FS_DEVICE_INFORMATION structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

