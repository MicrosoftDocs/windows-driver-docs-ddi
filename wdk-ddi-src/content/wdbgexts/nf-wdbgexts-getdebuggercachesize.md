---
UID: NF:wdbgexts.GetDebuggerCacheSize
title: GetDebuggerCacheSize function
author: windows-driver-content
description: The GetDebuggerCacheSize function returns the size of the cache that is used by the debugger to hold data that was obtained from the target.
old-location: debugger\getdebuggercachesize.htm
old-project: debugger
ms.assetid: 0365ffe5-575b-44a9-8711-837d499be8bc
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetDebuggerCacheSize, GetDebuggerCacheSize function [Windows Debugging], WdbgExts_Ref_da3c4b36-e7b1-429a-9d63-4f92101a189a.xml, debugger.getdebuggercachesize, wdbgexts/GetDebuggerCacheSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
-	wdbgexts.h
api_name:
-	GetDebuggerCacheSize
product: Windows
targetos: Windows
req.typenames: 
---

# GetDebuggerCacheSize function


## -description


The <b>GetDebuggerCacheSize</b> function returns the size of the cache that is used by the debugger to hold data that was obtained from the target.


## -parameters




### -param CacheSize [out]

Receives the size of the debugger's cache.


## -returns



If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.




## -remarks



The size of the cache can be set and retrieved by using the <a href="https://msdn.microsoft.com/638cb2e6-b333-4311-967c-d86c2e93b4ec">.cache</a> command.

Each target process has its own cache.  The returned size is the size of the cache for the current target.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562180">.cache (Set Cache Size)</a>
 

 

