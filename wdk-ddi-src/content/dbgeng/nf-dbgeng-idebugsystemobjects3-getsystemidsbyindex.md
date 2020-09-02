---
UID: NF:dbgeng.IDebugSystemObjects3.GetSystemIdsByIndex
title: IDebugSystemObjects3::GetSystemIdsByIndex (dbgeng.h)
description: The GetSystemIdsByIndex method returns the engine target IDs for the specified targets.
old-location: debugger\getsystemidsbyindex.htm
tech.root: debugger
ms.assetid: 7b2dcb75-f674-4a66-a483-8c3f644390c1
ms.date: 05/03/2018
keywords: ["IDebugSystemObjects3::GetSystemIdsByIndex"]
ms.keywords: GetSystemIdsByIndex, GetSystemIdsByIndex method [Windows Debugging], GetSystemIdsByIndex method [Windows Debugging],IDebugSystemObjects3 interface, GetSystemIdsByIndex method [Windows Debugging],IDebugSystemObjects4 interface, IDebugSystemObjects3 interface [Windows Debugging],GetSystemIdsByIndex method, IDebugSystemObjects3.GetSystemIdsByIndex, IDebugSystemObjects3::GetSystemIdsByIndex, IDebugSystemObjects4 interface [Windows Debugging],GetSystemIdsByIndex method, IDebugSystemObjects4::GetSystemIdsByIndex, IDebugSystemObjects_d1d7e689-407b-4d84-b1ce-75736b761089.xml, dbgeng/IDebugSystemObjects3::GetSystemIdsByIndex, dbgeng/IDebugSystemObjects4::GetSystemIdsByIndex, debugger.getsystemidsbyindex
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
 - IDebugSystemObjects3::GetSystemIdsByIndex
 - dbgeng/IDebugSystemObjects3::GetSystemIdsByIndex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSystemObjects3.GetSystemIdsByIndex
 - IDebugSystemObjects4.GetSystemIdsByIndex
---

# IDebugSystemObjects3::GetSystemIdsByIndex


## -description

The <b>GetSystemIdsByIndex</b> method returns the engine target IDs for the specified targets.

## -parameters

### -param Start 

[in]
Specifies the index of the first target whose target ID is requested.

### -param Count 

[in]
Specifies the number of processes whose IDs are requested.

### -param Ids 

[out]
Receives the engine target IDs.  If <i>Ids</i> is <b>NULL</b>, this information is not returned; otherwise, <i>Ids</i> is treated as an array of <i>Count</i> ULONG values.

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

The index of the first target is zero.  The index of the last target is the number of targets returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsystemobjects4-getnumbersystems">GetNumberSystems</a> minus one.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debugging-session-and-execution-model">Debugging Session and Execution Model</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>

