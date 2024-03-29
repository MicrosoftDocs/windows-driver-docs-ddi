---
UID: NF:dbgeng.IDebugSymbols3.GetImagePathWide
title: IDebugSymbols3::GetImagePathWide (dbgeng.h)
description: The GetImagePathWide method returns the executable image path.
old-location: debugger\getimagepathwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetImagePathWide"]
ms.keywords: GetImagePathWide, GetImagePathWide method [Windows Debugging], GetImagePathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetImagePathWide method, IDebugSymbols3.GetImagePathWide, IDebugSymbols3::GetImagePathWide, dbgeng/IDebugSymbols3::GetImagePathWide, debugger.getimagepathwide
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
 - IDebugSymbols3::GetImagePathWide
 - dbgeng/IDebugSymbols3::GetImagePathWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols3::GetImagePathWide
---

# IDebugSymbols3::GetImagePathWide


## -description

The <b>GetImagePathWide</b>  method returns the executable image path.

## -parameters

### -param Buffer [out, optional]


Receives the executable image path.  This is a string that contains directories separated by semicolons (<b>;</b>).  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize [in]


Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param PathSize [out, optional]


Receives the size, in characters, of the executable image path.

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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the executable image path and the path was truncated.

</td>
</tr>
</table>

## -remarks

The executable image path is used by the engine when searching for executable images.

The executable image path can consist of several directories separated by semicolons.  These directories are searched in order.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-appendimagepath">AppendImagePath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-setimagepath">SetImagePath</a>

