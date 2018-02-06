---
UID: NN:dbgeng.IDebugOutputCallbacks2
title: IDebugOutputCallbacks2
author: windows-driver-content
description: The IDebugOutputCallbacks2 interface allows clients to receive full debugger markup language (DML) content for presentation.
old-location: debugger\idebugoutputcallbacks2.htm
old-project: debugger
ms.assetid: D35D8960-AD9F-4493-B6CD-3E3049CC3BBD
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugoutputcallbacks2, IDebugOutputCallbacks2 interface [Windows Debugging], IDebugOutputCallbacks2 interface [Windows Debugging], described, IDebugOutputCallbacks2, dbgeng/IDebugOutputCallbacks2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
-	IDebugOutputCallbacks2
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugOutputCallbacks2 interface


## -description


The <b>IDebugOutputCallbacks2</b> interface allows clients to receive full  debugger markup language (DML) content for presentation. 

This interface extends the <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> interface, not the <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbackswide.md">IDebugOutputCallbacksWide</a> interface. Therefore, it can be passed in to the existing <a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a> method. 

The engine performs a <b>QueryInterface</b> for <b>IDebugOutputCallbacks2</b> to see which interface the incoming output callback object supports. If the object supports <b>IDebugOutputCallbacks2</b>, all output will be sent through the extended <b>IDebugOutputCallbacks2</b> methods.

An output object can register for both text and DML content, if it can handle them both. During output processing of the callback the engine will pick the format that reduces conversions, thus supporting both may reduce conversions in the engine. It is not necessary, though, and supporting only one format is the expected mode of operation.

The basic <a href="https://msdn.microsoft.com/library/windows/hardware/ff550815">IDebugOutputCallbacks::Output</a> method is not used. 


## -members

The <b>IDebugOutputCallbacks2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/BA710D92-63F4-4B4B-868A-58074FC052E9">GetInterestMask</a>
</td>
<td align="left" width="63%">
Allows the callback object to describe which kinds of output notifications it wants to receive. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553183">Output</a>
</td>
<td align="left" width="63%">
This method is not used.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2FFF9B54-6E77-4D46-B6C0-5BADD208BFCC">Output2</a>
</td>
<td align="left" width="63%">
Returns notifications for the <b>IDebugOutputCallbacks2</b> interface.

</td>
</tr>
</table>Allows the callback object to describe which kinds of output notifications it wants to receive. 

This method is not used.

Returns notifications for the <b>IDebugOutputCallbacks2</b> interface.

 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556751">SetOutputCallbacks</a>

<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbackswide.md">IDebugOutputCallbacksWide</a>

<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugOutputCallbacks2 interface%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

