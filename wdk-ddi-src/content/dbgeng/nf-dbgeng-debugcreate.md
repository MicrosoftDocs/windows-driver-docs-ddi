---
UID: NF:dbgeng.DebugCreate
title: DebugCreate function (dbgeng.h)
description: The DebugCreate function creates a new client object and returns an interface pointer to it.
old-location: debugger\debugcreate.htm
tech.root: debugger
ms.date: 02/06/2022
keywords: ["DebugCreate function"]
ms.keywords: ClientFns_4a96fd16-32b9-40f5-bc7f-60ae6ecadb32.xml, DebugCreate, DebugCreate function [Windows Debugging], dbgeng/DebugCreate, debugger.debugcreate
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DebugCreate
 - dbgeng/DebugCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - dbgeng.dll
api_name:
 - DebugCreate
---

# DebugCreate function


## -description

The <b>DebugCreate</b> function creates a new client object and returns an interface pointer to it.

## -parameters

### -param InterfaceId [in]


Specifies the interface identifier (IID) of the desired debugger engine client interface.  This is the type of the interface that will be returned in <i>Interface</i>. For information about the interface identifier, see <a href="/windows-hardware/drivers/debugger/using-client-objects">Using Client Objects</a>.

### -param Interface [out]


Receives an interface pointer for the new client.  The type of this interface is specified by <i>InterfaceId</i>.

## -returns

This method may also return other error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

The parameters passed to **DebugCreate** are the same as those passed to **IUnknown::QueryInterface**, and they are treated the same way.

As with **IUnknown::QueryInterface**, when the returned interface is no longer needed, its **IUnknown::Release** method should be called.

You don't need to call **CoInitialize**, **CoInitializeEx**, or **OleInitialize** to use this function and interfaces obtained by it.

The debugger engine client interfaces cannot be obtained by calling **CoCreateInstance**, **CoCreateInstanceEx**, or **CoGetClassObject**. Use **DebugCreate**, **DebugCreateEx**, **DebugConnect**, or **DebugConnectWide** to create such an interface, or call **IUnknown::QueryInterface** on another debugger engine client interface.

## -see-also

<a href="/windows-hardware/drivers/debugger/client-objects">Client Objects</a>
