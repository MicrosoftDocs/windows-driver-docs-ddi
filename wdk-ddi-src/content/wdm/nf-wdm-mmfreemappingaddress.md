---
UID: NF:wdm.MmFreeMappingAddress
title: MmFreeMappingAddress function (wdm.h)
description: The MmFreeMappingAddress routine frees a range of virtual memory reserved by the MmAllocateMappingAddress routine.
old-location: kernel\mmfreemappingaddress.htm
tech.root: kernel
ms.assetid: df5afc18-da83-46b4-b7ab-8cef4353b951
ms.date: 04/30/2018
keywords: ["MmFreeMappingAddress function"]
ms.keywords: MmFreeMappingAddress, MmFreeMappingAddress routine [Kernel-Mode Driver Architecture], k106_fa09359d-0552-429a-b3af-048f03ea7a15.xml, kernel.mmfreemappingaddress, wdm/MmFreeMappingAddress
f1_keywords:
 - "wdm/MmFreeMappingAddress"
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
- MmFreeMappingAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmFreeMappingAddress function


## -description


The <b>MmFreeMappingAddress</b> routine frees a range of virtual memory reserved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> routine. 


## -parameters




### -param BaseAddress [in]

Pointer to the beginning of the reserved memory buffer to free. This must be an address previously returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>.


### -param PoolTag [in]

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> that reserved the buffer. 


## -remarks



<b>MmFreeMappingAddress</b> frees a range of memory reserved by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>. If the memory range has already been mapped by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>, it must first be unmapped with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a> before the memory range can be freed. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a>
 

 

