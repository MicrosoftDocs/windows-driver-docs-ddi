---
UID: NF:wdm.ProbeForWrite
title: ProbeForWrite function
author: windows-driver-content
description: The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned.
old-location: kernel\probeforwrite.htm
old-project: kernel
ms.assetid: 8f435a52-f087-4d36-bf95-e82f5ab061e4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.probeforwrite, ProbeForWrite, k102_62889c29-62cb-43c2-ac19-e8b933783443.xml, ProbeForWrite routine [Kernel-Mode Driver Architecture], wdm/ProbeForWrite
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	ProbeForWrite
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ProbeForWrite function


## -description


The <b>ProbeForWrite</b> routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned. 


## -syntax


````
VOID ProbeForWrite(
  _Inout_ PVOID  Address,
  _In_    SIZE_T Length,
  _In_    ULONG  Alignment
);
````


## -parameters




### -param Address [in, out]

Specifies the beginning of the user-mode buffer.


### -param Length [in]

Specifies the length, in bytes, of the user-mode buffer.


### -param Alignment [in]

Specifies the required alignment, in bytes, of the beginning of the user-mode buffer.


## -returns


None



## -remarks


If the specified range of memory is not a valid user-mode address range or is not writable (no access, read-only, and so on), <b>ProbeForWrite</b> raises the STATUS_ACCESS_VIOLATION exception. If the beginning of the address range is not aligned on the byte boundary that is specified by <i>Alignment</i>, <b>ProbeForWrite</b> raises the STATUS_DATATYPE_MISALIGNMENT exception. 

Kernel-mode drivers must use <b>ProbeForWrite</b> to validate write access to buffers allocated in user space. It is most commonly used during METHOD_NEITHER I/O to validate the user buffer pointed to by <b>Irp-&gt;UserBuffer</b>.

Drivers must call <b>ProbeForWrite</b> inside a <b>try/except</b> block. If the routine raises an exception, the driver should complete the IRP with the appropriate error. Note that subsequent accesses by the driver to the user-mode buffer must also be encapsulated within a <b>try/except</b> block: a malicious application could have another thread deleting, substituting, or changing the protection of user address ranges at any time (even after or during a call to <b>ProbeForRead</b> or <b>ProbeForWrite</b>). For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

Do not use this routine on kernel-mode addresses; it will raise an exception.

If <b>Irp-&gt;RequestorMode</b> = <b>KernelMode</b>, the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> and <b>Irp-&gt;UserBuffer</b> fields do not contain user-mode addresses, and a call to <b>ProbeForWrite</b> to probe a buffer pointed to by either field will raise an exception.

If <i>Length</i> = 0, <b>ProbeForWrite</b> does no checking of the address. In this case, the routine does not raise an exception for an address that is misaligned or is outside the range of valid user addresses.



## -see-also

<a href="..\wdm\nf-wdm-probeforread.md">ProbeForRead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ProbeForWrite routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

