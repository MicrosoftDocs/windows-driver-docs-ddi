---
UID: NF:dbgeng.IDebugControl.GetRadix
title: IDebugControl::GetRadix (dbgeng.h)
description: The GetRadix method returns the default radix (number base) used by the debugger engine when it evaluates and displays MASM expressions, and when it displays symbol information.
old-location: debugger\getradix.htm
tech.root: debugger
ms.assetid: eae478e1-f70c-4344-a6e0-982a668c1f5d
ms.date: 05/03/2018
ms.keywords: GetRadix, GetRadix method [Windows Debugging], GetRadix method [Windows Debugging],IDebugControl interface, GetRadix method [Windows Debugging],IDebugControl2 interface, GetRadix method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetRadix method, IDebugControl.GetRadix, IDebugControl2 interface [Windows Debugging],GetRadix method, IDebugControl2::GetRadix, IDebugControl3 interface [Windows Debugging],GetRadix method, IDebugControl3::GetRadix, IDebugControl::GetRadix, IDebugControl_3f4cb732-868a-4944-bcd9-dd1f221824df.xml, dbgeng/IDebugControl2::GetRadix, dbgeng/IDebugControl3::GetRadix, dbgeng/IDebugControl::GetRadix, debugger.getradix
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl.GetRadix"
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
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl.GetRadix
- IDebugControl2.GetRadix
- IDebugControl3.GetRadix
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetRadix


## -description


The <b>GetRadix</b> method returns the default radix (number base) used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/introduction">debugger engine</a> when it evaluates and displays MASM expressions, and when it displays symbol information.


## -parameters




### -param Radix [out]

Receives the default radix.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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



For more information about the default radix, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/using-input-and-output">Using Input and Output</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-setradix">SetRadix</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/n--set-number-base-">n (Set Number Base)</a>
 

 

