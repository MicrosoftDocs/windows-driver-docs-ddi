---
UID: NF:dbgeng.IDebugControl3.GetPageSize
title: IDebugControl3::GetPageSize (dbgeng.h)
description: The GetPageSize method returns the page size for the effective processor mode.
old-location: debugger\getpagesize.htm
tech.root: debugger
ms.assetid: 26f11dfb-3fc3-4804-a294-2dfc674b4a73
ms.date: 05/03/2018
keywords: ["IDebugControl3::GetPageSize"]
ms.keywords: GetPageSize, GetPageSize method [Windows Debugging], GetPageSize method [Windows Debugging],IDebugControl interface, GetPageSize method [Windows Debugging],IDebugControl2 interface, GetPageSize method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetPageSize method, IDebugControl2 interface [Windows Debugging],GetPageSize method, IDebugControl2::GetPageSize, IDebugControl3 interface [Windows Debugging],GetPageSize method, IDebugControl3.GetPageSize, IDebugControl3::GetPageSize, IDebugControl::GetPageSize, IDebugControl_b38e4c0a-5992-4afe-b684-2eb65b3a0271.xml, dbgeng/IDebugControl2::GetPageSize, dbgeng/IDebugControl3::GetPageSize, dbgeng/IDebugControl::GetPageSize, debugger.getpagesize
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
 - IDebugControl3::GetPageSize
 - dbgeng/IDebugControl3::GetPageSize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl.GetPageSize
 - IDebugControl2.GetPageSize
 - IDebugControl3.GetPageSize
---

# IDebugControl3::GetPageSize


## -description

The <b>GetPageSize</b> method returns the page size for the effective processor mode.

## -parameters

### -param Size 

[out]
Receives the page size.

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

