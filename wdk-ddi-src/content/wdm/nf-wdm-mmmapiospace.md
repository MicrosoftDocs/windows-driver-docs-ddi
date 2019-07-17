---
UID: NF:wdm.MmMapIoSpace
title: MmMapIoSpace function (wdm.h)
description: The MmMapIoSpace routine maps the given physical address range to nonpaged system space.
old-location: kernel\mmmapiospace.htm
tech.root: kernel
ms.assetid: efc9eb0e-0e83-46db-a450-79b9472fedff
ms.date: 04/30/2018
ms.keywords: MmMapIoSpace, MmMapIoSpace routine [Kernel-Mode Driver Architecture], k106_65fbb44b-6b8a-408d-8945-8d2eba25ca7c.xml, kernel.mmmapiospace, wdm/MmMapIoSpace
ms.topic: function
f1_keywords:
 - "wdm/MmMapIoSpace"
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmMapIoSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmMapIoSpace function


## -description


The <b>MmMapIoSpace</b> routine maps the given physical address range to nonpaged system space.


## -parameters




### -param PhysicalAddress [in]

Specifies the starting physical address of the I/O range to be mapped.


### -param NumberOfBytes [in]

Specifies a value greater than zero, indicating the number of bytes to be mapped.


### -param CacheType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range.


## -returns



<b>MmMapIoSpace</b> returns the base virtual address that maps the base physical address for the range. If space for mapping the range is insufficient, it returns <b>NULL</b>.




## -remarks



A driver must call this routine during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MmMapIoSpace</b> maps the physical address returned in the resource list to a logical address through which the driver can access device registers.

For example, drivers of PIO devices that allocate long-term I/O buffers can call this routine to make such buffers accessible or to make device memory accessible.

For more information about using this routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mapping-bus-relative-addresses-to-virtual-addresses">Mapping Bus-Relative Addresses to Virtual Addresses</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-mmallocatenoncachedmemory">MmAllocateNonCachedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpages">MmMapLockedPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmunmapiospace">MmUnmapIoSpace</a>
 

 

