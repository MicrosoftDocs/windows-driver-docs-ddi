---
UID: NF:fltkernel.FltReleasePushLockEx
title: FltReleasePushLockEx function
author: windows-driver-content
description: The FltReleasePushLockEx routine releases a specified push lock owned by the current thread.
ms.assetid: 8ada42d3-1988-43fd-89f7-af0c5702e9c0
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: FltReleasePushLockEx
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: FltMgr.lib
req.dll: 
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	FltMgr.sys
api_name: 
-	FltReleasePushLockEx
product:
-	Windows
targetos: Windows

---

# FltReleasePushLockEx function


## -description

The **FltReleasePushLockEx** routine releases a specified push lock owned by the current thread.

## -parameters

### -param PushLock
The <b>FltReleasePushLock</b> routine releases a specified push lock owned by the current thread.

### -param Flags

A bitmask of flags that control the attributes of the lock.


## -remarks

<b>FltReleasePushLock</b> releases a push lock that was previously acquired by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541667">FltAcquirePushLockExclusive</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541672">FltAcquirePushLockShared</a>. 

Because <b>FltReleasePushLock</b> reenables normal kernel APC delivery, it is not necessary to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545908">FsRtlExitFileSystem</a> after calling <b>FltReleasePushLock</b>. 

## -see-also