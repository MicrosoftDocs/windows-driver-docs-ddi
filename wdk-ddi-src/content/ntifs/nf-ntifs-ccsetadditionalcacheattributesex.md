---
UID: NF:ntifs.CcSetAdditionalCacheAttributesEx
title: CcSetAdditionalCacheAttributesEx function (ntifs.h)
description: Call the CcSetAdditionalCacheAttributesEx routine to enable extended cache behavior on a cached file.
old-location: ifsk\ccsetadditionalcacheattributesex.htm
tech.root: ifsk
ms.assetid: 187719CD-5F0C-4AFD-BC00-ECD3C29A118F
ms.date: 04/16/2018
keywords: ["CcSetAdditionalCacheAttributesEx function"]
ms.keywords: CcSetAdditionalCacheAttributesEx, CcSetAdditionalCacheAttributesEx routine [Installable File System Drivers], ifsk.ccsetadditionalcacheattributesex, ntifs/CcSetAdditionalCacheAttributesEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetAdditionalCacheAttributesEx
 - ntifs/CcSetAdditionalCacheAttributesEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetAdditionalCacheAttributesEx
---

# CcSetAdditionalCacheAttributesEx function


## -description

Call the <b>CcSetAdditionalCacheAttributesEx</b> routine to enable extended cache behavior on a cached file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the cached file.

### -param Flags 

[in]
Behavior flags to set for <i>FileObject</i>. Currently, only the  <b>AGGRESSIVE_UNMAP_BEHIND</b> flag is available. Setting this flag will allow the cache manager to optimize memory usage when modified writes are disabled for a file object.

## -remarks

<b>CcSetAdditionalCacheAttributesEx</b> can be called any time after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539203">CcSetAdditionalCacheAttributes</a>

