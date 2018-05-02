---
UID: NF:dbgeng.IDebugSymbols2.GetModuleNameString
title: IDebugSymbols2::GetModuleNameString
author: windows-driver-content
description: The GetModuleNameString method returns the name of the specified module.
old-location: debugger\getmodulenamestring.htm
old-project: debugger
ms.assetid: 4264f5e1-08f5-4878-9e10-b98859043515
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetModuleNameString, GetModuleNameString method [Windows Debugging], GetModuleNameString method [Windows Debugging],IDebugSymbols2 interface, GetModuleNameString method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols2 interface [Windows Debugging],GetModuleNameString method, IDebugSymbols2.GetModuleNameString, IDebugSymbols2::GetModuleNameString, IDebugSymbols3 interface [Windows Debugging],GetModuleNameString method, IDebugSymbols3::GetModuleNameString, IDebugSymbols_e00a93fb-08c4-4f37-9915-577a22d9c889.xml, dbgeng/IDebugSymbols2::GetModuleNameString, dbgeng/IDebugSymbols3::GetModuleNameString, debugger.getmodulenamestring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugSymbols2.GetModuleNameString
-	IDebugSymbols3.GetModuleNameString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols2::GetModuleNameString


## -description


The <b>GetModuleNameString</b>  method returns the name of the specified module.


## -parameters




### -param Which [in]

Specifies which of the module's names to return, possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_MODNAME_IMAGE

</td>
<td>
The image name.  This is the name of the executable file, including the extension. Typically, the full path is included in user mode but not in kernel mode.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_MODULE

</td>
<td>
The module name. This is usually just the file name without the extension. In a few cases, the module name differs significantly from the file name.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_LOADED_IMAGE

</td>
<td>
The loaded image name.  Unless Microsoft CodeView symbols are present, this is the same as the image name.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_SYMBOL_FILE

</td>
<td>
The symbol file name.  The path and name of the symbol file. If no symbols have been loaded, this is the name of the executable file instead.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_MAPPED_IMAGE

</td>
<td>
The mapped image name.  In most cases, this is <b>NULL</b>. If the debugger is mapping an image file (for example, during minidump debugging), this is the name of the mapped image.

</td>
</tr>
</table>
 


### -param Index [in]

Specifies the index of the module.  If it is set to DEBUG_ANY_ID, the <i>Base</i> parameter is used to specify the location of the module instead.


### -param Base [in]

If <i>Index</i> is DEBUG_ANY_ID, specifies the location in the target's memory address space of the base of the module.  Otherwise it is ignored.


### -param Buffer [out, optional]

Receives the name of the module.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the buffer <i>Buffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the module's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful. However, the size of the buffer was smaller than the size of the module's name so it was truncated to fit in the buffer.

</td>
</tr>
</table>
 




## -remarks



For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547146">GetModuleNames</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

