---
UID: NF:dbgeng.IDebugSymbols3.GetModuleNames
title: IDebugSymbols3::GetModuleNames (dbgeng.h)
description: The GetModuleNames method returns the names of the specified module.
old-location: debugger\getmodulenames.htm
tech.root: debugger
ms.assetid: dd33f88a-91f6-4ea4-bb6b-6fb505676684
ms.date: 05/03/2018
keywords: ["IDebugSymbols3::GetModuleNames"]
ms.keywords: GetModuleNames, GetModuleNames method [Windows Debugging], GetModuleNames method [Windows Debugging],IDebugSymbols interface, GetModuleNames method [Windows Debugging],IDebugSymbols2 interface, GetModuleNames method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetModuleNames method, IDebugSymbols2 interface [Windows Debugging],GetModuleNames method, IDebugSymbols2::GetModuleNames, IDebugSymbols3 interface [Windows Debugging],GetModuleNames method, IDebugSymbols3.GetModuleNames, IDebugSymbols3::GetModuleNames, IDebugSymbols::GetModuleNames, IDebugSymbols_b200104b-e0e6-4470-80f9-d6904c346737.xml, dbgeng/IDebugSymbols2::GetModuleNames, dbgeng/IDebugSymbols3::GetModuleNames, dbgeng/IDebugSymbols::GetModuleNames, debugger.getmodulenames
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
 - IDebugSymbols3::GetModuleNames
 - dbgeng/IDebugSymbols3::GetModuleNames
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbols.GetModuleNames
 - IDebugSymbols2.GetModuleNames
 - IDebugSymbols3.GetModuleNames
---

# IDebugSymbols3::GetModuleNames


## -description

The <b>GetModuleNames</b> method returns the names of the specified module.

## -parameters

### -param Index 

[in]
Specifies the index of the module whose names are requested.  If it is set to DEBUG_ANY_ID, the module is specified by <i>Base</i>.

### -param Base 

[in]
Specifies the base address of the module whose names are requested.  This parameter is only used if <i>Index</i> is set to DEBUG_ANY_ID.

### -param ImageNameBuffer 

[out, optional]
Receives the image name of the module.  If <i>ImageNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param ImageNameBufferSize 

[in]
Specifies the size in characters of the buffer <i>ImageNameBuffer</i> in characters.

### -param ImageNameSize 

[out, optional]
Receives the size in characters of the image name.  If <i>ImageNameSize</i> is <b>NULL</b>, this information is not returned.

### -param ModuleNameBuffer 

[out, optional]
Receives the module name of the module.  If <i>ModuleNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param ModuleNameBufferSize 

[in]
Specifies the size in characters of the buffer <i>ModuleNameBuffer</i>.

### -param ModuleNameSize 

[out, optional]
Receives the size in characters of the module name.  If <i>ModuleNameSize</i> is <b>NULL</b>, this information is not returned.

### -param LoadedImageNameBuffer 

[out, optional]
Receives the loaded image name of the module.  If <i>LoadedImageNameBuffer</i> is <b>NULL</b>, this information is not returned.

### -param LoadedImageNameBufferSize 

[in]
Specifies the size in characters of the buffer <i>LoadedImageNameBuffer</i>.

### -param LoadedImageNameSize 

[out, optional]
Receives the size in characters of the loaded image name.  If <i>LoadedImageNameSize</i> is <b>NULL</b>, this information is not returned.

## -returns

This method may also return other error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful. However, at least one of <i>ImageNameBuffer</i>, <i>ModuleNameBuffer</i>, or <i>LoadedImageNameBuffer</i> was too small for the corresponding name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified module was not found.

</td>
</tr>
</table>

## -remarks

For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbols3-getmodulenamestring">GetModuleNameString</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols">IDebugSymbols</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols2">IDebugSymbols2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>

