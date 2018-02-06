---
UID: NF:dbgeng.IDebugRegisters2.GetIndexByName
title: IDebugRegisters2::GetIndexByName method
author: windows-driver-content
description: The GetIndexByName method returns the index of the named register.
old-location: debugger\getindexbyname.htm
old-project: debugger
ms.assetid: a012b235-ed50-4009-a7ee-01783f9e3597
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetIndexByName method [Windows Debugging], debugger.getindexbyname, IDebugRegisters::GetIndexByName, IDebugRegisters_5b85eaa4-3c90-47e0-9f7f-7f493617fa37.xml, GetIndexByName method [Windows Debugging], IDebugRegisters interface, IDebugRegisters2 interface [Windows Debugging], GetIndexByName method, dbgeng/IDebugRegisters2::GetIndexByName, IDebugRegisters2, GetIndexByName, IDebugRegisters2::GetIndexByName, GetIndexByName method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging], GetIndexByName method, dbgeng/IDebugRegisters::GetIndexByName
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugRegisters.GetIndexByName
-	IDebugRegisters2.GetIndexByName
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugRegisters2::GetIndexByName method


## -description


The <b>GetIndexByName</b> method returns the index of the named register.


## -syntax


````
HRESULT GetIndexByName(
  [in]  PCSTR  Name,
  [out] PULONG Index
);
````


## -parameters




### -param Name [in]

Specifies the name of the register whose index is requested.


### -param Index [out]

Receives the index of the register.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The register was not found.

</td>
</tr>
</table> 



## -remarks


For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.


