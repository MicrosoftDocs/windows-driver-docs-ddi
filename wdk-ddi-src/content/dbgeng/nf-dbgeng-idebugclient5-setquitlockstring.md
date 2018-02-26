---
UID: NF:dbgeng.IDebugClient5.SetQuitLockString
title: IDebugClient5::SetQuitLockString method
author: windows-driver-content
description: Sets a quit lock string.
old-location: debugger\idebugclient5_setquitlockstring.htm
old-project: debugger
ms.assetid: 0C4888C7-B7F9-4B23-8AC9-41CB7863AF22
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 5, :, C, D, I, IDebugClient5, IDebugClient5 interface [Windows Debugging], SetQuitLockString method, IDebugClient5::SetQuitLockString, L, Q, S, SetQuitLockString method [Windows Debugging], SetQuitLockString method [Windows Debugging], IDebugClient5 interface, SetQuitLockString,IDebugClient5.SetQuitLockString, b, c, dbgeng/IDebugClient5::SetQuitLockString, debugger.idebugclient5_setquitlockstring, e, g, i, k, l, n, o, r, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient5.SetQuitLockString
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::SetQuitLockString method


## -description


Sets a quit lock string. 


## -syntax


````
HRESULT SetQuitLockString(
  [in] PCSTR String
);
````


## -parameters




### -param String [in]

A pointer to the quit lock string.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    This function provides control over locking the session against
    undesired quits.  




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::SetQuitLockString method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

