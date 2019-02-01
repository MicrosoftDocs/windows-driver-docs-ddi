---
UID: NE:wdm._POOL_TYPE
title: _POOL_TYPE (wdm.h)
description: The POOL_TYPE enumeration type specifies the type of system memory to allocate.
old-location: kernel\pool_type.htm
tech.root: kernel
ms.assetid: a3dd0c74-3835-4f03-8b62-08954baaffe7
ms.date: 04/30/2018
ms.keywords: DontUseThisType, DontUseThisTypeSession, MaxPoolType, NonPagedPool, NonPagedPoolBase, NonPagedPoolBaseCacheAligned, NonPagedPoolBaseCacheAlignedMustS, NonPagedPoolBaseMustSucceed, NonPagedPoolCacheAligned, NonPagedPoolCacheAlignedMustS, NonPagedPoolCacheAlignedMustSSession, NonPagedPoolCacheAlignedSession, NonPagedPoolExecute, NonPagedPoolMustSucceed, NonPagedPoolMustSucceedSession, NonPagedPoolNx, NonPagedPoolNxCacheAligned, NonPagedPoolSession, NonPagedPoolSessionNx, POOL_TYPE, POOL_TYPE enumeration [Kernel-Mode Driver Architecture], PagedPool, PagedPoolCacheAligned, PagedPoolCacheAlignedSession, PagedPoolSession, _POOL_TYPE, kernel.pool_type, sysenum_90446d42-0e73-4da3-a3df-27efe3daa67b.xml, wdm/DontUseThisType, wdm/DontUseThisTypeSession, wdm/MaxPoolType, wdm/NonPagedPool, wdm/NonPagedPoolBase, wdm/NonPagedPoolBaseCacheAligned, wdm/NonPagedPoolBaseCacheAlignedMustS, wdm/NonPagedPoolBaseMustSucceed, wdm/NonPagedPoolCacheAligned, wdm/NonPagedPoolCacheAlignedMustS, wdm/NonPagedPoolCacheAlignedMustSSession, wdm/NonPagedPoolCacheAlignedSession, wdm/NonPagedPoolExecute, wdm/NonPagedPoolMustSucceed, wdm/NonPagedPoolMustSucceedSession, wdm/NonPagedPoolNx, wdm/NonPagedPoolNxCacheAligned, wdm/NonPagedPoolSession, wdm/NonPagedPoolSessionNx, wdm/POOL_TYPE, wdm/PagedPool, wdm/PagedPoolCacheAligned, wdm/PagedPoolCacheAlignedSession, wdm/PagedPoolSession
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	POOL_TYPE
product:
- Windows
targetos: Windows
req.typenames: POOL_TYPE
---

# _POOL_TYPE enumeration


## -description


The <b>POOL_TYPE</b> enumeration type specifies the type of system memory to allocate.


## -enum-fields




### -field NonPagedPool

<i>Nonpaged pool</i>, which is nonpageable system memory. Nonpaged pool can be accessed from any IRQL, but it is a scarce resource and drivers should allocate it only when necessary.

System memory allocated with the <b>NonPagedPool</b> pool type is executable. For more information, see the description of the <b>NonPagedPoolExecute</b> pool type.

Starting with Windows 8, drivers should allocate most or all of their nonpaged memory from the no-execute (NX) nonpaged pool instead of the executable nonpaged pool. For more information, see the description of the <b>NonPagedPoolNx</b> pool type.


### -field NonPagedPoolExecute

Starting with Windows 8, <b>NonPagedPoolExecute</b> is an alternate name for the <b>NonPagedPool</b> value. This value indicates that the allocated memory is to be nonpaged and executable—that is, instruction execution is enabled in this memory. To port a driver from an earlier version of Windows, you should typically replace all or most instances of the <b>NonPagedPool</b> name in the driver source code with <b>NonPagedPoolNx</b>. Avoid replacing instances of the <b>NonPagedPool</b> name with <b>NonPagedPoolExecute</b> except in cases in which executable memory is explicitly required. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh920391">No-Execute (NX) Nonpaged Pool</a>.


### -field PagedPool

<i>Paged pool</i>, which is pageable system memory. Paged pool can only be allocated and accessed at IRQL &lt; DISPATCH_LEVEL.


### -field NonPagedPoolMustSucceed

This value is <u>for internal use only</u>, and is allowed only during system startup. Drivers must not specify this value at times other than system startup, because a "must succeed" request crashes the system if the requested memory size is unavailable.


### -field DontUseThisType

Reserved for system use.


### -field NonPagedPoolCacheAligned

Nonpaged pool, aligned on processor cache boundaries. This value is <u>for internal use only</u>.


### -field PagedPoolCacheAligned

Paged pool, aligned on processor cache boundaries. This value is <u>for internal use only</u>.


### -field NonPagedPoolCacheAlignedMustS

This value is <u>for internal use only</u>, and is allowed only during system startup. It is the cache-aligned equivalent of <b>NonPagedPoolMustSucceed</b>.


### -field MaxPoolType

Reserved for system use.


### -field NonPagedPoolBase

Reserved for system use.


### -field NonPagedPoolBaseMustSucceed

Reserved for system use.


### -field NonPagedPoolBaseCacheAligned

Reserved for system use.


### -field NonPagedPoolBaseCacheAlignedMustS

Reserved for system use.


### -field NonPagedPoolSession

Deprecated. Do not use.


### -field PagedPoolSession

Deprecated. Do not use.


### -field NonPagedPoolMustSucceedSession

Deprecated. Do not use.


### -field DontUseThisTypeSession

Deprecated. Do not use.


### -field NonPagedPoolCacheAlignedSession

Deprecated. Do not use.


### -field PagedPoolCacheAlignedSession

Deprecated. Do not use.


### -field NonPagedPoolCacheAlignedMustSSession

Deprecated. Do not use.


### -field NonPagedPoolNx

<i>No-execute</i> (NX) nonpaged pool. This pool type is available starting with Windows 8. In contrast to the nonpaged pool designated by <b>NonPagedPool</b>, which allocates executable memory, the NX nonpaged pool  allocates memory in which instruction execution is disabled. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh920391">No-Execute (NX) Nonpaged Pool</a>.

Nonpaged pool can be accessed from any IRQL, but it is a scarce resource and drivers should allocate it only when necessary.


### -field NonPagedPoolNxCacheAligned

NX nonpaged pool, aligned on processor cache boundaries. This value is reserved for exclusive use by the operating system.


### -field NonPagedPoolSessionNx

Reserved for exclusive use by the operating system.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544523">ExAllocatePoolWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545298">ExInitializeLookasideListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545301">ExInitializeNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545309">ExInitializePagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563679">SeAssignSecurityEx</a>
 

 

