---
UID: NF:wdm.ProbeForWrite
title: ProbeForWrite function (wdm.h)
description: The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.
old-location: kernel\probeforwrite.htm
tech.root: kernel
ms.assetid: 8f435a52-f087-4d36-bf95-e82f5ab061e4
ms.date: 04/30/2018
ms.keywords: ProbeForWrite, ProbeForWrite routine [Kernel-Mode Driver Architecture], k102_62889c29-62cb-43c2-ac19-e8b933783443.xml, kernel.probeforwrite, wdm/ProbeForWrite
ms.topic: function
f1_keywords:
 - "wdm/ProbeForWrite"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ProbeForWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# ProbeForWrite function


## -description


The <b>ProbeForWrite</b> routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned. 


## -parameters




### -param Address [in, out]

Specifies the beginning of the user-mode buffer.


### -param Length [in]

Specifies the length, in bytes, of the user-mode buffer.


### -param Alignment [in]

Specifies the required alignment, in bytes, of the beginning of the user-mode buffer.


## -remarks



If the specified range of memory is not a valid user-mode address range or is not writable (no access, read-only, and so on), <b>ProbeForWrite</b> raises the STATUS_ACCESS_VIOLATION exception. If the beginning of the address range is not aligned on the byte boundary that is specified by <i>Alignment</i>, <b>ProbeForWrite</b> raises the STATUS_DATATYPE_MISALIGNMENT exception. 

Kernel-mode drivers must use <b>ProbeForWrite</b> to validate write access to buffers allocated in user space. It is most commonly used during METHOD_NEITHER I/O to validate the user buffer pointed to by <b>Irp->UserBuffer</b>.

Drivers must call <b>ProbeForWrite</b> inside a <b>try/except</b> block. If the routine raises an exception, the driver should complete the IRP with the appropriate error. Note that subsequent accesses by the driver to the user-mode buffer must also be encapsulated within a <b>try/except</b> block: a malicious application could have another thread deleting, substituting, or changing the protection of user address ranges at any time (even after or during a call to <b>ProbeForRead</b> or <b>ProbeForWrite</b>). For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>.

Do not use this routine on kernel-mode addresses; it will raise an exception.

If <b>Irp->RequestorMode</b> = <b>KernelMode</b>, the <b>Irp->AssociatedIrp.SystemBuffer</b> and <b>Irp->UserBuffer</b> fields do not contain user-mode addresses, and a call to <b>ProbeForWrite</b> to probe a buffer pointed to by either field will raise an exception.

If <i>Length</i> = 0, <b>ProbeForWrite</b> does no checking of the address. In this case, the routine does not raise an exception for an address that is misaligned or is outside the range of valid user addresses.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a>
 

 

