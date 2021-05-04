---
UID: NF:ntifs.CcSetAdditionalCacheAttributes
title: CcSetAdditionalCacheAttributes function (ntifs.h)
description: Call the CcSetAdditionalCacheAttributes routine to enable or disable read-ahead (also called &#0034;lazy read&#0034;) or write-behind (also called &#0034;lazy write&#0034;) on a cached file.
old-location: ifsk\ccsetadditionalcacheattributes.htm
tech.root: ifsk
ms.date: 01/15/2021
keywords: ["CcSetAdditionalCacheAttributes function"]
ms.keywords: CcSetAdditionalCacheAttributes, CcSetAdditionalCacheAttributes routine [Installable File System Drivers], ccref_a9722d17-3140-4bcd-abd9-46d31fa13174.xml, ifsk.ccsetadditionalcacheattributes, ntifs/CcSetAdditionalCacheAttributes
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetAdditionalCacheAttributes
 - ntifs/CcSetAdditionalCacheAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetAdditionalCacheAttributes
---

# CcSetAdditionalCacheAttributes function

## -description

Call the **CcSetAdditionalCacheAttributes** routine to enable or disable read-ahead (also called "lazy read") or write-behind (also called "lazy write") on a cached file.

## -parameters

### -param FileObject

[in] Pointer to a file object for the cached file.

### -param DisableReadAhead

[in] Boolean value set to **TRUE** to disable read-ahead, or **FALSE** to enable it.

### -param DisableWriteBehind

[in] Boolean value set to **TRUE** to disable write-behind, or **FALSE** to enable it.

## -remarks

**CcSetAdditionalCacheAttributes** can be called any time after calling [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md). Initially, both read-ahead and write-behind are enabled.

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcReadAhead**](/previous-versions/ff539191(v=vs.85))

[**CcSetReadAheadGranularity**](nf-ntifs-ccsetreadaheadgranularity.md)
