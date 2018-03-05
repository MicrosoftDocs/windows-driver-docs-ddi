---
UID: NF:dbgeng.IDebugRegisters.GetNumberRegisters
title: IDebugRegisters::GetNumberRegisters method
author: windows-driver-content
description: The GetNumberRegisters method returns the number of registers on the target computer.
old-location: debugger\getnumberregisters.htm
old-project: debugger
ms.assetid: 51c521fc-e89c-49c9-8110-de31af3bed83
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNumberRegisters method [Windows Debugging], GetNumberRegisters method [Windows Debugging], IDebugRegisters interface, GetNumberRegisters method [Windows Debugging], IDebugRegisters2 interface, GetNumberRegisters,IDebugRegisters.GetNumberRegisters, IDebugRegisters, IDebugRegisters interface [Windows Debugging], GetNumberRegisters method, IDebugRegisters2 interface [Windows Debugging], GetNumberRegisters method, IDebugRegisters2::GetNumberRegisters, IDebugRegisters::GetNumberRegisters, IDebugRegisters_b2fa1d95-0331-4c27-a3af-3cc8e895e88f.xml, dbgeng/IDebugRegisters2::GetNumberRegisters, dbgeng/IDebugRegisters::GetNumberRegisters, debugger.getnumberregisters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugRegisters.GetNumberRegisters
-	IDebugRegisters2.GetNumberRegisters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters::GetNumberRegisters method


## -description


The <b>GetNumberRegisters</b> method returns the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a> on the target computer.


## -syntax


````
HRESULT GetNumberRegisters(
  [out] PULONG Number
);
````


## -parameters




### -param Number [out]

Receives the number of registers on the target's computer.


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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



For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.



