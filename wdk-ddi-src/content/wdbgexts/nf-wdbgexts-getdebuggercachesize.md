---
UID: NF:wdbgexts.GetDebuggerCacheSize
title: GetDebuggerCacheSize function
author: windows-driver-content
description: The GetDebuggerCacheSize function returns the size of the cache that is used by the debugger to hold data that was obtained from the target.
old-location: debugger\getdebuggercachesize.htm
old-project: debugger
ms.assetid: 0365ffe5-575b-44a9-8711-837d499be8bc
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , C, D, G, GetDebuggerCacheSize, GetDebuggerCacheSize function [Windows Debugging], S, WdbgExts_Ref_da3c4b36-e7b1-429a-9d63-4f92101a189a.xml, a, b, c, debugger.getdebuggercachesize, e, g, h, i, r, t, u, wdbgexts/GetDebuggerCacheSize, z"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	GetDebuggerCacheSize
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetDebuggerCacheSize function


## -description


The <b>GetDebuggerCacheSize</b> function returns the size of the cache that is used by the debugger to hold data that was obtained from the target.


## -syntax


````
__inline BOOL GetDebuggerCacheSize(
  _Out_ PULONG64 CacheSize
);
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GetDebuggerCacheSize function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

