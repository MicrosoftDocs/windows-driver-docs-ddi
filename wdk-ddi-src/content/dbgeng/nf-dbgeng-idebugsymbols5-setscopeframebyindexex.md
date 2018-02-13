---
UID: NF:dbgeng.IDebugSymbols5.SetScopeFrameByIndexEx
title: IDebugSymbols5::SetScopeFrameByIndexEx method
author: windows-driver-content
description: Sets the current frame by using an index.
old-location: debugger\idebugsymbols5_setscopeframebyindexex.htm
old-project: debugger
ms.assetid: E0638C55-4160-48A5-9378-6AA9AAC8DC36
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetScopeFrameByIndexEx method [Windows Debugging], dbgeng/IDebugSymbols5::SetScopeFrameByIndexEx, SetScopeFrameByIndexEx method [Windows Debugging], IDebugSymbols5 interface, SetScopeFrameByIndexEx, debugger.idebugsymbols5_setscopeframebyindexex, IDebugSymbols5 interface [Windows Debugging], SetScopeFrameByIndexEx method, IDebugSymbols5, IDebugSymbols5::SetScopeFrameByIndexEx
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
-	Dbgeng.h
apiname:
-	IDebugSymbols5.SetScopeFrameByIndexEx
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols5::SetScopeFrameByIndexEx method


## -description


Sets the current frame by using an index.


## -syntax


````
HRESULT SetScopeFrameByIndexEx(
  [in] ULONG Flags,
  [in] ULONG Index
);
````


## -parameters




### -param Flags [in]

A bit-set that contains options that affect the behavior of this method. 


### -param Index [in]

An index by which to set the frame.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols5.md">IDebugSymbols5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols5::SetScopeFrameByIndexEx method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

