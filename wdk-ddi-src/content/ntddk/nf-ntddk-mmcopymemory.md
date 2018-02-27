---
UID: NF:ntddk.MmCopyMemory
title: MmCopyMemory function
author: windows-driver-content
description: The MmCopyMemory routine copies the specified range of virtual or physical memory into the caller-supplied buffer.
old-location: kernel\mmcopymemory.htm
old-project: kernel
ms.assetid: 2B5492CD-B24D-44B5-BDAE-0B43A1AF1FCA
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MmCopyMemory, MmCopyMemory routine [Kernel-Mode Driver Architecture], kernel.mmcopymemory, ntddk/MmCopyMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	MmCopyMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmCopyMemory function


## -description


The <b>MmCopyMemory</b> routine copies the specified range of virtual or physical memory into the caller-supplied buffer.


## -syntax


````
NTSTATUS MmCopyMemory(
  _In_  PVOID           TargetAddress,
  _In_  MM_COPY_ADDRESS SourceAddress,
  _In_  SIZE_T          NumberOfBytes,
  _In_  ULONG           Flags,
  _Out_ PSIZE_T         NumberOfBytesTransferred
);
````


## -parameters




### -param TargetAddress [in]

A pointer to a caller-supplied buffer. This buffer must be in nonpageable  memory.


### -param SourceAddress [in]

An <a href="..\ntddk\ns-ntddk-_mm_copy_address.md">MM_COPY_ADDRESS</a> structure, passed by value, that contains either the virtual address or the physical address of the data to be copied to the buffer pointed to by <i>TargetAddress</i>.


### -param NumberOfBytes [in]

The number of bytes to copy from <i>SourceAddress</i> to <i>TargetAddress</i>.


### -param Flags [in]

Flags that indicate whether <i>SourceAddress</i> is a virtual address or a physical address. The following flag bits are defined for this parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Description</th>
</tr>
<tr>
<td>MM_COPY_MEMORY_PHYSICAL</td>
<td><i>SourceAddress</i> specifies a physical address.</td>
</tr>
<tr>
<td>MM_COPY_MEMORY_VIRTUAL</td>
<td><i>SourceAddress</i> specifies a virtual address.</td>
</tr>
</table>
 

These two flag bits are mutually exclusive. The caller must set one or the other, but not both.


### -param NumberOfBytesTransferred [out]

A pointer to a location to which the routine writes the number of bytes successfully copied from the <i>SourceAddress</i> location to the buffer at <i>TargetAddress</i>.


## -returns



<b>MmCopyMemory</b> returns STATUS_SUCCESS if the entire range has been copied successfully. Otherwise, an error status is returned and the caller must inspect the output value pointed to by the <i>NumberOfBytesTransferred</i> parameter to determine how many bytes were actually copied.




## -remarks



Kernel-mode drivers can call this routine to safely access arbitrary physical or virtual addresses.

If the MM_COPY_MEMORY_PHYSICAL flag is set, <i>SourceAddress</i> should point to regular memory that is under control of the operating system. <b>MmCopyMemory</b> will return an error status code for physical addresses that refer to I/O space, which includes memory-mapped devices and firmware tables. To access physical memory in I/O space, drivers can use the <a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a> routine.

If the MM_COPY_MEMORY_VIRTUAL flag is set, <i>SourceAddress</i> can point to either a buffer in system address space, or a buffer in the user address space of the current process. If the caller does not control the lifetime of the allocation containing the specified source address, <b>MmCopyMemory</b> might fail or might return inconsistent data, but will not cause a system crash—even for system addresses that are invalid and would trigger a bug check if referenced directly. <b>MmCopyMemory</b> will return an error status code for system virtual addresses that refer to I/O space.

If memory at the virtual address specified by <i>SourceAddress</i> is not resident, <b>MmCopyMemory</b> will try to make it resident.




## -see-also

<a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>



<a href="..\ntddk\ns-ntddk-_mm_copy_address.md">MM_COPY_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmCopyMemory routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

