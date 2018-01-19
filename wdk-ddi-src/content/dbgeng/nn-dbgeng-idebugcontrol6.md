---
UID: NN:dbgeng.IDebugControl6
title: IDebugControl6
author: windows-driver-content
description: .
old-location: debugger\idebugcontrol6.htm
old-project: debugger
ms.assetid: 3361EB55-0765-405E-AA75-D1DF3BDE0003
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
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
req.alt-api: IDebugControl6
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl6 interface



## -description




## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugControl6</b> interface inherits from <a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>. <b>IDebugControl6</b> also has these types of members:

The <b>IDebugControl6</b> interface has these methods.

The GetExecutionStatusEx method returns information about the execution status of the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.

The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.

 


## -members
The <b>IDebugControl6</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818569">GetExecutionStatusEx</a>
</td>
<td align="left" width="63%">
The GetExecutionStatusEx method returns information about the execution status of the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/dn818570">GetSynchronizationStatus</a>
</td>
<td align="left" width="63%">
The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.

</td>
</tr>
</table>The GetExecutionStatusEx method returns information about the execution status of the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.

The GetSynchronizationStatus method returns information about the synchronization status of the debugger engine.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl6 interface%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

