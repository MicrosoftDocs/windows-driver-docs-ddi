---
UID: NE:wdm._POOL_TYPE
title: _POOL_TYPE
author: windows-driver-content
description: The POOL_TYPE enumeration type specifies the type of system memory to allocate.
old-location: kernel\pool_type.htm
old-project: kernel
ms.assetid: a3dd0c74-3835-4f03-8b62-08954baaffe7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _POOL_TYPE, POOL_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: POOL_TYPE
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: POOL_TYPE
req.product: Windows 10 or later.
---

# _POOL_TYPE enumeration



## -description
The <b>POOL_TYPE</b> enumeration type specifies the type of system memory to allocate.



## -syntax

````
typedef enum _POOL_TYPE { 
  NonPagedPool,
  NonPagedPoolExecute                   = NonPagedPool,
  PagedPool,
  NonPagedPoolMustSucceed               = NonPagedPool + 2,
  DontUseThisType,
  NonPagedPoolCacheAligned              = NonPagedPool + 4,
  PagedPoolCacheAligned,
  NonPagedPoolCacheAlignedMustS         = NonPagedPool + 6,
  MaxPoolType,
  NonPagedPoolBase                      = 0,
  NonPagedPoolBaseMustSucceed           = NonPagedPoolBase + 2,
  NonPagedPoolBaseCacheAligned          = NonPagedPoolBase + 4,
  NonPagedPoolBaseCacheAlignedMustS     = NonPagedPoolBase + 6,
  NonPagedPoolSession                   = 32,
  PagedPoolSession                      = NonPagedPoolSession + 1,
  NonPagedPoolMustSucceedSession        = PagedPoolSession + 1,
  DontUseThisTypeSession                = NonPagedPoolMustSucceedSession + 1,
  NonPagedPoolCacheAlignedSession       = DontUseThisTypeSession + 1,
  PagedPoolCacheAlignedSession          = NonPagedPoolCacheAlignedSession + 1,
  NonPagedPoolCacheAlignedMustSSession  = PagedPoolCacheAlignedSession + 1,
  NonPagedPoolNx                        = 512,
  NonPagedPoolNxCacheAligned            = NonPagedPoolNx + 4,
  NonPagedPoolSessionNx                 = NonPagedPoolNx + 32
} POOL_TYPE;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtagpriority.md">ExAllocatePoolWithTagPriority</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554322">LookasideListAllocateEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-seassignsecurityex.md">SeAssignSecurityEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POOL_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

