---
UID: NF:dbgeng.IDebugBreakpoint3.GetGuid
title: IDebugBreakpoint3::GetGuid method
author: windows-driver-content
description: Returns a GUID for the breakpoint.
old-location: debugger\idebugbreakpoint3_getguid.htm
old-project: debugger
ms.assetid: 0D279F79-FFA8-4661-A9E9-EFA62A97EEC7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., 3, :, B, D, G, GetGuid method [Windows Debugging], GetGuid method [Windows Debugging], IDebugBreakpoint3 interface, GetGuid,IDebugBreakpoint3.GetGuid, I, IDebugBreakpoint3, IDebugBreakpoint3 interface [Windows Debugging], GetGuid method, IDebugBreakpoint3::GetGuid, a, b, d, dbgeng/IDebugBreakpoint3::GetGuid, debugger.idebugbreakpoint3_getguid, e, g, i, k, n, o, p, r, t, u"
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
-	IDebugBreakpoint3.GetGuid
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugBreakpoint3::GetGuid method


## -description


Returns a GUID for the breakpoint.


## -syntax


````
HRESULT GetGuid(
  [out] LPGUID Guid
);
````


## -parameters




### -param Guid [out]

A unique ID returned for the breakpoint.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugbreakpoint3.md">IDebugBreakpoint3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugBreakpoint3::GetGuid method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

