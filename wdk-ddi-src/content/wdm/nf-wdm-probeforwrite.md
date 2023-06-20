---
UID: NF:wdm.ProbeForWrite
title: ProbeForWrite function (wdm.h)
description: The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.
old-location: kernel\probeforwrite.htm
tech.root: kernel
ms.date: 05/22/2023
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

> [!WARNING]
> The **ProbeForWrite** function is not recommended for use in current software, and is included for historical compatibility only. Use [**ProbeForRead**](./nf-wdm-probeforread.md) instead when validating user buffers. See Remarks for more info.

The <b>ProbeForWrite</b> routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.

## -parameters

### -param Address [in, out]


Specifies the beginning of the user-mode buffer.

### -param Length [in]


Specifies the length, in bytes, of the user-mode buffer. See additional information in the Remarks section.

### -param Alignment [in]


Specifies the required alignment, in bytes, of the beginning of the user-mode buffer.

## -remarks

This function typically provides no substantial benefit over [**ProbeForRead**](./nf-wdm-probeforread.md) because a robust driver must always be prepared to handle protection changes in the user mode virtual address space, including protection changes that remove write permission to a buffer passed to a driver after a **ProbeForWrite** call has executed.  Because **ProbeForWrite** accesses each page in the supplied buffer, performance may be reduced due to the overhead of accessing each page, especially if the supplied buffer describes a large region of virtual address space.  In addition, because **ProbeForWrite** writes to each page, the same buffer may not be used safely  with multiple concurrent driver requests.  For these reasons, new driver code should always use **ProbeForRead** instead.

The following table outlines the properties of each kernel mode buffer probing routine:

|Behavior|**ProbeForRead**|**ProbeForWrite**|
|-|-|-|
|Confirms that buffer describes a region in user mode address space, if the length is non-zero|x|x|
|Confirms that buffer base address and length do not wrap past maximum pointer value|x|x|
|Confirms that buffer is aligned to requested alignment boundary, if the length is non-zero|x|x|
|Confirms that buffer is initially writable (may change at any time if user mode application reprotects its address space)| |x|
|Accesses each page in the buffer (additional overhead)| |x|
|Modifies each page in the buffer (may cause unexpected behavior if same buffer is used in parallel with multiple driver requests)| |x|

Historically, on certain processors which did not honor read only permissions for kernel mode code, there were meaningful functional differences between **ProbeForWrite** and **ProbeForRead**.  In these cases, the operating system previously relied on **ProbeForWrite** performing an explicit paging writability check.  This distinction is no longer meaningful for any processors that are supported by Windows NT 4.0 or later.

### Legacy remarks

Kernel-mode drivers may use <b>ProbeForWrite</b> to validate write access to buffers allocated in user space. It is most commonly used during METHOD_NEITHER I/O to validate the user buffer pointed to by <b>Irp->UserBuffer</b>.

If the specified range of memory is not a valid user-mode address range or is not writable (no access, read-only, and so on), <b>ProbeForWrite</b> raises the STATUS_ACCESS_VIOLATION exception. If the beginning of the address range is not aligned on the byte boundary that is specified by <i>Alignment</i>, <b>ProbeForWrite</b> raises the STATUS_DATATYPE_MISALIGNMENT exception.

Drivers must call <b>ProbeForWrite</b> inside a <b>try/except</b> block. If the routine raises an exception, the driver should complete the IRP with the appropriate error. Note that subsequent accesses by the driver to the user-mode buffer must also be encapsulated within a <b>try/except</b> block: a malicious application could have another thread deleting, substituting, or changing the protection of user address ranges at any time (even after or during a call to <b>ProbeForRead</b> or <b>ProbeForWrite</b>). For more information, see <a href="/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>.

Do not use this routine on kernel-mode addresses; it will raise an exception.

If <b>Irp->RequestorMode</b> = <b>KernelMode</b>, the <b>Irp->AssociatedIrp.SystemBuffer</b> and <b>Irp->UserBuffer</b> fields do not contain user-mode addresses, and a call to <b>ProbeForWrite</b> to probe a buffer pointed to by either field will raise an exception.

If <i>Length</i> = 0, <b>ProbeForWrite</b> does no checking of the address. In this case, the routine does not raise an exception for an address that is misaligned or is outside the range of valid user addresses.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-probeforread">ProbeForRead</a>
