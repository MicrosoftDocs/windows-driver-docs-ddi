---
UID: NF:dbgeng.DebugCreateEx
title: DebugCreateEx function (dbgeng.h)
description: The DebugCreateEx function creates a new client object and returns an interface pointer to it.
old-location: debugger\debugcreateex.htm
tech.root: debugger
ms.assetid: 851A9461-E085-4BDA-BB69-603F6932BFA6
ms.date: 05/03/2018
ms.keywords: DebugCreateEx, DebugCreateEx function [Windows Debugging], dbgeng/DebugCreateEx, debugger.debugcreateex
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- dbgeng.dll
api_name:
- DebugCreateEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# DebugCreateEx function


## -description


The <b>DebugCreateEx</b> function creates a new <a href="https://msdn.microsoft.com/173a67f1-093e-4462-8e2c-41d0f10106d0">client object</a> and returns an interface pointer to it.


## -parameters




### -param InterfaceId [in]

Specifies the interface identifier (IID) of the desired debugger engine client interface.  This is the type of the interface that will be returned in <i>Interface</i>. For information about the interface identifier, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a>.


### -param DbgEngOptions [in]

Supplies debugger option flags.


### -param Interface [out]

Receives an interface pointer for the new client.  The type of this interface is specified by <i>InterfaceId</i>.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The function was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE </b></dt>
</dl>
</td>
<td width="60%">
The client object doesn't implement the specified interface.

</td>
</tr>
</table>
 




## -remarks



The parameters passed to <b>DebugCreateEx</b> are the same as those passed to <b>IUnknown::QueryInterface</b>, and they are treated the same way.

As with <b>IUnknown::QueryInterface</b>, when the returned interface is no longer needed, its <b>IUnknown::Release</b> method should be called.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539137">Client Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>
 

 

