---
UID: NF:wdm.ProbeForWrite
title: ProbeForWrite function (wdm.h)
description: The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.
old-location: kernel\probeforwrite.htm
tech.root: kernel
ms.date: 05/09/2023
keywords: ["ProbeForWrite function"]
ms.keywords: ProbeForWrite, ProbeForWrite routine [Kernel-Mode Driver Architecture], k102_62889c29-62cb-43c2-ac19-e8b933783443.xml, kernel.probeforwrite, wdm/ProbeForWrite
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ProbeForWrite
 - wdm/ProbeForWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ProbeForWrite
---

# ProbeForWrite function


## -description

The <b>ProbeForWrite</b> routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.

## -parameters

### -param Address [in, out]


Specifies the beginning of the user-mode buffer.

### -param Length [in]


Specifies the length, in bytes, of the user-mode buffer. See additional information in the Remarks section.

### -param Alignment [in]


Specifies the required alignment, in bytes, of the beginning of the user-mode buffer.

## -remarks

Kernel-mode drivers may use <b>ProbeForWrite</b> to validate write access to buffers allocated in user space. It is most commonly used during METHOD_NEITHER I/O to validate the user buffer pointed to by <b>Irp->UserBuffer</b>.

If the specified range of memory is not a valid user-mode address range or is not writable (no access, read-only, and so on), <b>ProbeForWrite</b> raises the STATUS_ACCESS_VIOLATION exception. If the beginning of the address range is not aligned on the byte boundary that is specified by <i>Alignment</i>, <b>ProbeForWrite</b> raises the STATUS_DATATYPE_MISALIGNMENT exception. 

Drivers must call <b>ProbeForWrite</b> inside a <b>try/except</b> block. If the routine raises an exception, the driver should complete the IRP with the appropriate error. Note that subsequent accesses by the driver to the user-mode buffer must also be encapsulated within a <b>try/except</b> block: a malicious application could have another thread deleting, substituting, or changing the protection of user address ranges at any time (even after or during a call to <b>ProbeForRead</b> or <b>ProbeForWrite</b>). For more information, see <a href="/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>.

Each virtual memory page of the buffer range is tested for write. This adds overhead to each kernel call and can cause performance problems if, for instance, the entire range of the buffer is not actually going to be used during a kernel request. Because of this, and because the status of the virtual memory pages can change after <b>ProbeForWrite</b>, use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a> instead to avoid this overhead.

Do not use this routine on kernel-mode addresses; it will raise an exception.

If <b>Irp->RequestorMode</b> = <b>KernelMode</b>, the <b>Irp->AssociatedIrp.SystemBuffer</b> and <b>Irp->UserBuffer</b> fields do not contain user-mode addresses, and a call to <b>ProbeForWrite</b> to probe a buffer pointed to by either field will raise an exception.

If <i>Length</i> = 0, <b>ProbeForWrite</b> does no checking of the address. In this case, the routine does not raise an exception for an address that is misaligned or is outside the range of valid user addresses.

**ProbeForWrite** can cause performance issues if the supplied buffer is significantly larger than the actual amount of data written to the buffer. To improve performance, probe only the portion of the buffer that the driver will write to, or use [**ProbeForRead**](./nf-wdm-probeforread.md) for reduced overhead.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a>
