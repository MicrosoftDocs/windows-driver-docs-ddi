---
UID: NS:wdm._FILE_IS_REMOTE_DEVICE_INFORMATION
title: "_FILE_IS_REMOTE_DEVICE_INFORMATION"
author: windows-driver-content
description: The FILE_IS_REMOTE_DEVICE_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine.
old-location: kernel\file_is_remote_device_information.htm
old-project: kernel
ms.assetid: E1A82D24-A981-414A-83D8-E71F97E0301A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PFILE_IS_REMOTE_DEVICE_INFORMATION, FILE_IS_REMOTE_DEVICE_INFORMATION, FILE_IS_REMOTE_DEVICE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_IS_REMOTE_DEVICE_INFORMATION, PFILE_IS_REMOTE_DEVICE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_IS_REMOTE_DEVICE_INFORMATION, kernel.file_is_remote_device_information, wdm/FILE_IS_REMOTE_DEVICE_INFORMATION, wdm/PFILE_IS_REMOTE_DEVICE_INFORMATION"
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
-	FILE_IS_REMOTE_DEVICE_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_IS_REMOTE_DEVICE_INFORMATION, *PFILE_IS_REMOTE_DEVICE_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_IS_REMOTE_DEVICE_INFORMATION structure


## -description


The <b>FILE_IS_REMOTE_DEVICE_INFORMATION</b> structure is used as an argument to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> routine.


## -struct-fields




### -field IsRemote

A value that indicates whether the file system that contains the file is a remote file system.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
 

 

