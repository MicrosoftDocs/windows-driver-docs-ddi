---
UID: NF:wdm.IoAllocateMdl
title: IoAllocateMdl function
author: windows-driver-content
description: The IoAllocateMdl routine allocates a memory descriptor list (MDL) large enough to map a buffer, given the buffer's starting address and length. Optionally, this routine associates the MDL with an IRP.
old-location: kernel\ioallocatemdl.htm
old-project: kernel
ms.assetid: c06cb000-837d-4ee9-baa1-0217ad8b14cb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoAllocateMdl routine [Kernel-Mode Driver Architecture], IoAllocateMdl, kernel.ioallocatemdl, k104_8f4336cd-03b0-4ca2-9538-182970594ba3.xml, wdm/IoAllocateMdl
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoAllocateMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoAllocateMdl function


## -description


The <b>IoAllocateMdl</b> routine allocates a memory descriptor list (MDL) large enough to map a buffer, given the buffer's starting address and length. Optionally, this routine associates the MDL with an IRP. 


## -syntax


````
PMDL IoAllocateMdl(
  _In_opt_    PVOID   VirtualAddress,
  _In_        ULONG   Length,
  _In_        BOOLEAN SecondaryBuffer,
  _In_        BOOLEAN ChargeQuota,
  _Inout_opt_ PIRP    Irp
);
````


## -parameters




### -param VirtualAddress [in, optional]

Pointer to the base virtual address of the buffer the MDL is to describe.


### -param Length [in]

Specifies the length, in bytes, of the buffer that the MDL is to describe. For more information, see the following Remarks section.


### -param SecondaryBuffer [in]

Indicates whether the buffer is a primary or secondary buffer. This parameter determines how the MDL is to be linked to the IRP. All buffers except the first buffer described by an MDL in an IRP are considered secondary buffers. This field must be <b>FALSE</b> if no IRP is associated with the MDL. For more information, see the following Remarks section.


### -param ChargeQuota [in]

Reserved for system use. Drivers must set this parameter to <b>FALSE</b>.


### -param Irp [in, out, optional]

Pointer to an IRP to be associated with the MDL. If the <i>Irp</i> pointer is non-<b>NULL</b>, the allocated MDL is associated with the specified IRP's MDL list, according to the value of <i>SecondaryBuffer</i>. 


## -returns



<b>IoAllocateMdl</b> returns a pointer to an MDL, or, if the MDL cannot be allocated, it returns <b>NULL</b>. 




## -remarks



<b>IoAllocateMdl</b> can be used by a driver that needs to break a buffer into pieces, each mapped by a separate MDL, or to map a driver-allocated buffer. The driver should call <a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a> with the MDL allocated by this call to set up an MDL describing a driver-allocated buffer in nonpaged pool.

The <i>Length</i> parameter specifies the size of the buffer that is to be described by the MDL. In Windows Server 2003, Windows XP, and Windows 2000, the maximum buffer size, in bytes, that this routine can allocate is PAGE_SIZE * (65535 - <b>sizeof</b>(MDL)) / <b>sizeof</b>(ULONG_PTR). In Windows Vista and Windows Server 2008, the maximum buffer size is (2 gigabytes - PAGE_SIZE). In Windows 7 and Windows Server 2008 R2, the maximum buffer size is (4 gigabytes - PAGE_SIZE).

If the <i>SecondaryBuffer</i> parameter is <b>FALSE</b>, the routine updates <i>Irp</i>-&gt;<b>MdlAddress</b> to point to the new MDL. If <i>SecondaryBuffer</i> is <b>TRUE</b>, the routine adds the MDL to the end of the MDL chain that <i>Irp</i>-&gt;<b>MdlAddress</b> points to.

For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>. 




## -see-also

<a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>



<a href="..\wdm\nf-wdm-iobuildpartialmdl.md">IoBuildPartialMdl</a>



<a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAllocateMdl routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

