---
UID: NF:dbgeng.IDebugControl2.IsPointer64Bit
title: IDebugControl2::IsPointer64Bit (dbgeng.h)
description: The IsPointer64Bit method determines if the effective processor uses 64-bit pointers.
old-location: debugger\ispointer64bit.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::IsPointer64Bit"]
ms.keywords: IDebugControl interface [Windows Debugging],IsPointer64Bit method, IDebugControl2 interface [Windows Debugging],IsPointer64Bit method, IDebugControl2.IsPointer64Bit, IDebugControl2::IsPointer64Bit, IDebugControl3 interface [Windows Debugging],IsPointer64Bit method, IDebugControl3::IsPointer64Bit, IDebugControl::IsPointer64Bit, IDebugControl_62a0cc8d-e542-4889-9f68-591d00828d4b.xml, IsPointer64Bit, IsPointer64Bit method [Windows Debugging], IsPointer64Bit method [Windows Debugging],IDebugControl interface, IsPointer64Bit method [Windows Debugging],IDebugControl2 interface, IsPointer64Bit method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::IsPointer64Bit, dbgeng/IDebugControl3::IsPointer64Bit, dbgeng/IDebugControl::IsPointer64Bit, debugger.ispointer64bit
req.header: dbgeng.h
req.include-header: 
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
 - IDebugControl2::IsPointer64Bit
 - dbgeng/IDebugControl2::IsPointer64Bit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.IsPointer64Bit
 - IDebugControl2.IsPointer64Bit
 - IDebugControl3.IsPointer64Bit
---

# IDebugControl2::IsPointer64Bit


## -description

The <b>IsPointer64Bit</b> method determines if the effective processor uses 64-bit pointers.

## -returns

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
The effective processor uses 64-bit pointers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The effective processor does not use 64-bit pointers.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.
