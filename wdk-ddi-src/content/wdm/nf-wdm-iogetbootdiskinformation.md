---
UID: NF:wdm.IoGetBootDiskInformation
title: IoGetBootDiskInformation function (wdm.h)
description: The IoGetBootDiskInformation routine returns information describing the boot and system disks.
old-location: kernel\iogetbootdiskinformation.htm
tech.root: kernel
ms.assetid: 744d5eae-2bdf-46b0-9412-f73e55939d8b
ms.date: 04/30/2018
ms.keywords: IoGetBootDiskInformation, IoGetBootDiskInformation routine [Kernel-Mode Driver Architecture], k104_11afe919-6902-4f53-9006-57cc4be126f1.xml, kernel.iogetbootdiskinformation, wdm/IoGetBootDiskInformation
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetBootDiskInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetBootDiskInformation function


## -description


The <b>IoGetBootDiskInformation</b> routine returns information describing the boot and system disks.


## -parameters




### -param BootDiskInformation [in, out]

Pointer to a caller-allocated buffer that the routine uses to return information about the boot and system disks. The routine fills this buffer in with either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540652">BOOTDISK_INFORMATION</a> or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540653">BOOTDISK_INFORMATION_EX</a> structure.


### -param Size [in]

Specifies the size, in bytes, of the buffer specified by <i>BootDiskInformation</i>. Should be either <b>sizeof</b>(<b>BOOTDISK_INFORMATION</b>) or <b>sizeof</b>(<b>BOOTDISK_INFORMATION_EX</b>).


## -returns



<b>IoGetBootDiskInformation</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the requested information in the buffer specified by <i>BootDiskInformation</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>Size</i> is less than the size, in bytes, of a <b>BOOTDISK_INFORMATION</b> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TOO_LATE</b></dt>
</dl>
</td>
<td width="60%">
The driver called the routine after the system has already booted. Only boot and system drivers can call <b>IoGetBootDiskInformation</b>, and then only in their <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routines.

</td>
</tr>
</table>
 




## -remarks



<b>IoGetBootDiskInformation</b> can be called only by a boot driver. This driver should call <b>IoGetBootDiskInformation</b> in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561022">Reinitialize</a> callback routine that the driver registers by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549494">IoRegisterBootDriverReinitialization</a> routine.

On Windows XP and later versions of Windows, if the <i>Size</i> parameter is <b>sizeof</b>(<b>BOOTDISK_INFORMATION_EX</b>) or larger, the routine returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540653">BOOTDISK_INFORMATION_EX</a> structure in the <i>BootDiskInformation</i> buffer. Otherwise, if <i>Size</i> is at least <b>sizeof</b>(<b>BOOTDISK_INFORMATION</b>), the routine returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540652">BOOTDISK_INFORMATION</a> structure.

On Windows 2000, the routine returns only the <b>BOOTDISK_INFORMATION</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540652">BOOTDISK_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540653">BOOTDISK_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549494">IoRegisterBootDriverReinitialization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561022">Reinitialize</a>
 

 

