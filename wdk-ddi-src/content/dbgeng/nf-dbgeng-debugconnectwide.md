---
UID: NF:dbgeng.DebugConnectWide
title: DebugConnectWide function
author: windows-driver-content
description: The DebugConnect and DebugConnectWide functions create a new client object and return an interface pointer to it. The client object will be connected to a remote host.
old-location: debugger\debugconnectwide.htm
tech.root: debugger
ms.assetid: B25AD9E0-FBDA-4E4F-A268-92C9AA761191
ms.date: 5/3/2018
ms.keywords: DebugConnectWide, DebugConnectWide function [Windows Debugging], dbgeng/DebugConnectWide, debugger.debugconnectwide
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	DllExport
api_location:
-	dbgeng.dll
api_name:
-	DebugConnectWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# DebugConnectWide function


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540465">DebugConnect</a> and <b>DebugConnectWide</b> functions create a new <a href="https://msdn.microsoft.com/173a67f1-093e-4462-8e2c-41d0f10106d0">client object</a> and return an interface pointer to it.  The client object will be connected to a remote host.


## -parameters




### -param RemoteOptions [in]

Specifies how the debugger engine will connect to the remote host.  These are the same options that get passed to the <b>-remote</b> option on the command line.  For details on the syntax of this string, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537819">Activating a Debugging Client</a>.


### -param InterfaceId [in]

Specifies the interface identifier (IID) of the desired debugger engine client interface.  This is the type of the interface that will be returned in <i>Interface</i>. For information about the interface identifier, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a>.


### -param Interface [out]

Receives an interface pointer for the new client.  The type of this interface is specified by <i>InterfaceId</i>.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



As with <b>IUnknown::QueryInterface</b>, when the returned interface is no longer needed, its <b>IUnknown::Release</b> method should be called. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539137">Client Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>
 

 

