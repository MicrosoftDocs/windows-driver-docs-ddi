---
UID: NF:dbgeng.IDebugSymbols3.AppendImagePathWide
title: IDebugSymbols3::AppendImagePathWide (dbgeng.h)
description: The AppendImagePathWide method appends directories to the executable image path.
old-location: debugger\appendimagepathwide.htm
tech.root: debugger
ms.assetid: 9a129ce5-4493-4838-9a6c-8a3c054e7c27
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::AppendImagePathWide"]
ms.keywords: AppendImagePathWide, AppendImagePathWide method [Windows Debugging], AppendImagePathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AppendImagePathWide method, IDebugSymbols3.AppendImagePathWide, IDebugSymbols3::AppendImagePathWide, dbgeng/IDebugSymbols3::AppendImagePathWide, debugger.appendimagepathwide
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
 - IDebugSymbols3::AppendImagePathWide
 - dbgeng/IDebugSymbols3::AppendImagePathWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugSymbols3.AppendImagePathWide
---

# IDebugSymbols3::AppendImagePathWide


## -description

The <b>AppendImagePathWide</b>  method appends directories to the executable image path.

## -parameters

### -param Addition 

[in]
Specifies the directories to append to the executable image path.  This is a string that contains directory names separated by semicolons (;).

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
The method was successful.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

The executable image path is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/e">engine</a> when searching for executable images.

The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getimagepath">GetImagePath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setimagepath">SetImagePath</a>

