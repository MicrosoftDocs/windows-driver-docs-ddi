---
UID: NF:ntddk.RtlVolumeDeviceToDosName
title: RtlVolumeDeviceToDosName function (ntddk.h)
description: The RtlVolumeDeviceToDosName routine is obsolete for Windows XP and later versions of Windows. Use IoVolumeDeviceToDosName instead.RtlVolumeDeviceToDosName returns the MS-DOS path for a specified device object that represents a file system volume.
old-location: kernel\rtlvolumedevicetodosname.htm
tech.root: kernel
ms.assetid: e25db70f-04bf-4fb1-8ff5-2beb4c825797
ms.date: 04/30/2018
ms.keywords: RtlVolumeDeviceToDosName, RtlVolumeDeviceToDosName routine [Kernel-Mode Driver Architecture], k109_a95aea8c-1156-4852-b4eb-38d2f141fcca.xml, kernel.rtlvolumedevicetodosname, ntddk/RtlVolumeDeviceToDosName
ms.topic: function
f1_keywords:
 - "ntddk/RtlVolumeDeviceToDosName"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete for Microsoft Windows XP and later versions of Windows. Use IoVolumeDeviceToDosName instead.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlVolumeDeviceToDosName
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlVolumeDeviceToDosName function


## -description


The <b>RtlVolumeDeviceToDosName</b> routine is <u>obsolete</u> for Windows XP and later versions of Windows. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iovolumedevicetodosname">IoVolumeDeviceToDosName</a> instead.

<b>RtlVolumeDeviceToDosName</b> returns the MS-DOS path for a specified device object that represents a file system volume.


## -parameters




### -param VolumeDeviceObject [in]

Pointer to a device object that represents a volume device object created by a storage class driver.


### -param DosName [out]

Pointer to a Unicode string containing the MS-DOS path of the volume device object specified by <i>VolumeDeviceObject</i>. 


## -returns



<b>RtlVolumeDeviceToDosName</b> returns STATUS_SUCCESS or an appropriate error status.




## -remarks



The behavior of this routine is identical to that of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iovolumedevicetodosname">IoVolumeDeviceToDosName</a>. For more information about how to use this routine, see <b>IoVolumeDeviceToDosName</b>.

Drivers that must work on older NT-based operating systems may use this routine. Drivers written for Windows XP and later must use <b>IoVolumeDeviceToDosName</b> instead.



