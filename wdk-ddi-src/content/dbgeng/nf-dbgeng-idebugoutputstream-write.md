---
UID: NF:dbgeng.IDebugOutputStream.Write
title: IDebugOutputStream::Write method
author: windows-driver-content
description: Writes to the debug output stream.
old-location: debugger\idebugoutputstream_write.htm
old-project: debugger
ms.assetid: CC609DA8-9778-4AFC-9205-5F68AF15927C
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Write method [Windows Debugging], IDebugOutputStream interface, IDebugOutputStream, Write, debugger.idebugoutputstream_write, dbgeng/IDebugOutputStream::Write, IDebugOutputStream interface [Windows Debugging], Write method, Write method [Windows Debugging], IDebugOutputStream::Write
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
-	IDebugOutputStream.Write
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugOutputStream::Write method


## -description


Writes to the debug output stream.


## -syntax


````
HRESULT Write(
  [in] PCWSTR psz
);
````


## -parameters




### -param psz [in]

A pointer to a Unicode character string of content to write.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugoutputstream.md">IDebugOutputStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugOutputStream::Write method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

