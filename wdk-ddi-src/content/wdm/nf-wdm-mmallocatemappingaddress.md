---
UID: NF:wdm.MmAllocateMappingAddress
title: MmAllocateMappingAddress function
author: windows-driver-content
description: The MmAllocateMappingAddress routine reserves a range of system virtual address space of the specified size.
old-location: kernel\mmallocatemappingaddress.htm
old-project: kernel
ms.assetid: e8d5fea6-d0fd-4dc4-b8ec-10c72381285b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/MmAllocateMappingAddress, k106_3ef2863e-218c-4546-a934-152cbd0133e9.xml, kernel.mmallocatemappingaddress, MmAllocateMappingAddress routine [Kernel-Mode Driver Architecture], MmAllocateMappingAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmAllocateMappingAddress
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmAllocateMappingAddress function


## -description


The <b>MmAllocateMappingAddress</b> routine reserves a range of system virtual address space of the specified size.


## -syntax


````
PVOID MmAllocateMappingAddress(
  _In_ SIZE_T NumberOfBytes,
  _In_ ULONG  PoolTag
);
````


## -parameters




### -param NumberOfBytes [in]

Specifies the number of bytes to reserve. 


### -param PoolTag [in]

Specifies a four-character tag used to identify the buffer. Use a distinct <i>PoolTag</i> tag for each allocation code path. For a description of pool tags, see <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. 


## -returns


<b>MmAllocateMappingAddress</b> returns a pointer to the beginning of the reserved memory buffer.



## -remarks


<b>MmAllocateMappingAddress</b> reserves a system virtual address range for the caller to use. No physical memory is allocated for the virtual address range and the virtual memory cannot be accessed until it is mapped by the <a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a> routine. The caller unmaps the reserved memory range by calling the <a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a> routine. Finally, the caller can free the reserved range by calling <a href="..\wdm\nf-wdm-mmfreemappingaddress.md">MmFreeMappingAddress</a>. 



## -see-also

<a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a>

<a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>

<a href="..\wdm\nf-wdm-mmfreemappingaddress.md">MmFreeMappingAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateMappingAddress routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

