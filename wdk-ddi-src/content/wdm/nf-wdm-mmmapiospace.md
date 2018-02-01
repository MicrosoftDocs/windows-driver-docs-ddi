---
UID: NF:wdm.MmMapIoSpace
title: MmMapIoSpace function
author: windows-driver-content
description: The MmMapIoSpace routine maps the given physical address range to nonpaged system space.
old-location: kernel\mmmapiospace.htm
old-project: kernel
ms.assetid: efc9eb0e-0e83-46db-a450-79b9472fedff
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmMapIoSpace, kernel.mmmapiospace, k106_65fbb44b-6b8a-408d-8945-8d2eba25ca7c.xml, MmMapIoSpace routine [Kernel-Mode Driver Architecture], wdm/MmMapIoSpace
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmMapIoSpace
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmMapIoSpace function


## -description


The <b>MmMapIoSpace</b> routine maps the given physical address range to nonpaged system space.


## -syntax


````
PVOID MmMapIoSpace(
  _In_ PHYSICAL_ADDRESS    PhysicalAddress,
  _In_ SIZE_T              NumberOfBytes,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````


## -parameters




### -param PhysicalAddress [in]

Specifies the starting physical address of the I/O range to be mapped.


### -param NumberOfBytes [in]

Specifies a value greater than zero, indicating the number of bytes to be mapped.


### -param CacheType [in]

Specifies a <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range.


## -returns


<b>MmMapIoSpace</b> returns the base virtual address that maps the base physical address for the range. If space for mapping the range is insufficient, it returns <b>NULL</b>.



## -remarks


A driver must call this routine during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MmMapIoSpace</b> maps the physical address returned in the resource list to a logical address through which the driver can access device registers.

For example, drivers of PIO devices that allocate long-term I/O buffers can call this routine to make such buffers accessible or to make device memory accessible.

For more information about using this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>. 



## -see-also

<a href="..\wdm\nf-wdm-mmallocatecontiguousmemory.md">MmAllocateContiguousMemory</a>

<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>

<a href="..\wdm\nf-wdm-mmunmapiospace.md">MmUnmapIoSpace</a>

<a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmMapIoSpace routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

