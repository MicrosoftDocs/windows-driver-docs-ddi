---
UID: NF:dbgeng.IDebugClient5.GetOutputLinePrefixWide
title: IDebugClient5::GetOutputLinePrefixWide method
author: windows-driver-content
description: Gets a Unicode character string prefix for output lines.
old-location: debugger\idebugclient5_getoutputlineprefixwide.htm
old-project: debugger
ms.assetid: 145A478E-826B-4E82-B358-6140D3A4063F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 5, :, C, D, G, GetOutputLinePrefixWide method [Windows Debugging], GetOutputLinePrefixWide method [Windows Debugging], IDebugClient5 interface, GetOutputLinePrefixWide,IDebugClient5.GetOutputLinePrefixWide, I, IDebugClient5, IDebugClient5 interface [Windows Debugging], GetOutputLinePrefixWide method, IDebugClient5::GetOutputLinePrefixWide, L, O, P, W, b, d, dbgeng/IDebugClient5::GetOutputLinePrefixWide, debugger.idebugclient5_getoutputlineprefixwide, e, f, g, i, l, n, p, r, t, u, x"
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
-	IDebugClient5.GetOutputLinePrefixWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::GetOutputLinePrefixWide method


## -description


Gets a Unicode character string prefix for output lines.


## -syntax


````
HRESULT GetOutputLinePrefixWide(
  [out]           _writes_opt_(BufferSize) PWSTR Buffer,
  [in]            ULONG                          BufferSize,
  [out, optional] PULONG                         PrefixSize
);
````


## -parameters




### -param Buffer [out]

The pointer to the buffer of the prefix.


### -param BufferSize [in]

The length of the buffer.


### -param PrefixSize [out, optional]

A pointer to the length of the prefix.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetOutputLinePrefixWide method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

