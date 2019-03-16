---
UID: NF:wdm.ProbeForRead
title: ProbeForRead function (wdm.h)
description: The ProbeForRead routine checks that a user-mode buffer actually resides in the user portion of the address space, and is correctly aligned.
old-location: kernel\probeforread.htm
tech.root: kernel
ms.assetid: 86b09f5c-6527-447e-b383-b97d45a57ce7
ms.date: 04/30/2018
ms.keywords: ProbeForRead, ProbeForRead routine [Kernel-Mode Driver Architecture], k102_a0260886-9f28-408e-91a1-fde07974ef9b.xml, kernel.probeforread, wdm/ProbeForRead
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ProbeForRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# ProbeForRead function


## -description


The <b>ProbeForRead</b> routine checks that a user-mode buffer actually resides in the user portion of the address space, and is correctly aligned. 


## -parameters




### -param Address [in]

Specifies the beginning of the user-mode buffer.


### -param Length [in]

Specifies the length, in bytes, of the user-mode buffer.


### -param Alignment [in]

Specifies the required alignment, in bytes, of the beginning of the user-mode buffer.


## -returns



None




## -remarks



If the specified range of memory is not within the user-mode address range, <b>ProbeForRead</b> raises the STATUS_ACCESS_VIOLATION exception. If the beginning of the address range is not aligned on the byte boundary that is specified by <i>Alignment</i>, <b>ProbeForRead</b> raises the STATUS_DATATYPE_MISALIGNMENT exception.

Kernel-mode drivers must use <b>ProbeForRead</b> to validate read access to buffers that are allocated in user space. It is most commonly used during METHOD_NEITHER I/O to validate the user buffer pointed to by <b>Irp -&gt; UserBuffer</b>.

Drivers must call <b>ProbeForRead</b> inside a <b>try/except</b> block. If the routine raises an exception, the driver should complete the IRP with the appropriate error. Note that subsequent accesses by the driver to the user-mode buffer must also be encapsulated within a <b>try/except</b> block: a malicious application could have another thread deleting, substituting, or changing the protection of user address ranges at any time (even after or during a call to <b>ProbeForRead</b> or <b>ProbeForWrite</b>). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

Do not use this routine on kernel-mode addresses; it will raise an exception.

If <b>Irp-&gt;RequestorMode</b> = <b>KernelMode</b>, the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> and <b>Irp-&gt;UserBuffer</b> fields do not contain user-mode addresses, and a call to <b>ProbeForRead</b> to probe a buffer pointed to by either field will raise an exception.

If <i>Length</i> = 0, <b>ProbeForRead</b> does no checking of the address. In this case, the routine does not raise an exception for an address that is misaligned or is outside the range of valid user addresses.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559879">ProbeForWrite</a>
 

 

