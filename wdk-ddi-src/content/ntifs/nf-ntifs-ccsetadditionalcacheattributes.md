---
UID: NF:ntifs.CcSetAdditionalCacheAttributes
title: CcSetAdditionalCacheAttributes function
author: windows-driver-content
description: Call the CcSetAdditionalCacheAttributes routine to enable or disable read-ahead (also called &#0034;lazy read&#0034;) or write-behind (also called &#0034;lazy write&#0034;) on a cached file.
old-location: ifsk\ccsetadditionalcacheattributes.htm
tech.root: ifsk
ms.assetid: 2f891543-0222-45c8-97cd-719ec5dd2fa8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcSetAdditionalCacheAttributes, CcSetAdditionalCacheAttributes routine [Installable File System Drivers], ccref_a9722d17-3140-4bcd-abd9-46d31fa13174.xml, ifsk.ccsetadditionalcacheattributes, ntifs/CcSetAdditionalCacheAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcSetAdditionalCacheAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcSetAdditionalCacheAttributes function


## -description


Call the <b>CcSetAdditionalCacheAttributes</b> routine to enable or disable read-ahead (also called "lazy read") or write-behind (also called "lazy write") on a cached file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file.


### -param DisableReadAhead [in]

Set to <b>TRUE</b> to disable read-ahead, <b>FALSE</b> to enable it. The caller must specify a value for <i>DisableReadAhead</i> in each call to <b>CcSetAdditionalCacheAttributes</b>, even if a value was already specified in a previous call.


### -param DisableWriteBehind [in]

Set to <b>TRUE</b> to disable write-behind, <b>FALSE</b> to enable it. The caller must specify a value for <i>DisableWriteBehind</i> in each call to <b>CcSetAdditionalCacheAttributes</b>, even if a value was already specified in a previous call.


## -returns



None




## -remarks



<b>CcSetAdditionalCacheAttributes</b> can be called any time after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>. Initially, both read-ahead and write-behind are enabled.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a>
 

 

