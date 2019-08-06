---
UID: NF:wdm.MmAllocateMappingAddress
title: MmAllocateMappingAddress function (wdm.h)
description: The MmAllocateMappingAddress routine reserves a range of system virtual address space of the specified size.
old-location: kernel\mmallocatemappingaddress.htm
tech.root: kernel
ms.assetid: e8d5fea6-d0fd-4dc4-b8ec-10c72381285b
ms.date: 04/30/2018
ms.keywords: MmAllocateMappingAddress, MmAllocateMappingAddress routine [Kernel-Mode Driver Architecture], k106_3ef2863e-218c-4546-a934-152cbd0133e9.xml, kernel.mmallocatemappingaddress, wdm/MmAllocateMappingAddress
ms.topic: function
f1_keywords:
 - "wdm/MmAllocateMappingAddress"
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmAllocateMappingAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmAllocateMappingAddress function


## -description


The <b>MmAllocateMappingAddress</b> routine reserves a range of system virtual address space of the specified size.


## -parameters




### -param NumberOfBytes [in]

Specifies the number of bytes to reserve. 


### -param PoolTag [in]

Specifies a four-character tag used to identify the buffer. Use a distinct <i>PoolTag</i> tag for each allocation code path. For a description of pool tags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>. 


## -returns



<b>MmAllocateMappingAddress</b> returns a pointer to the beginning of the reserved memory buffer.




## -remarks



<b>MmAllocateMappingAddress</b> reserves a system virtual address range for the caller to use. No physical memory is allocated for the virtual address range and the virtual memory cannot be accessed until it is mapped by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a> routine. The caller unmaps the reserved memory range by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a> routine. Finally, the caller can free the reserved range by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a>
 

 

