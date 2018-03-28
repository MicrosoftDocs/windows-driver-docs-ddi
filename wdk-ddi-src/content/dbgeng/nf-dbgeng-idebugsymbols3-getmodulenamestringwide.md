---
UID: NF:dbgeng.IDebugSymbols3.GetModuleNameStringWide
title: IDebugSymbols3::GetModuleNameStringWide method
author: windows-driver-content
description: The GetModuleNameStringWide method returns the name of the specified module.
old-location: debugger\getmodulenamestringwide.htm
old-project: debugger
ms.assetid: e1b756b9-394a-4ec4-845e-867460998086
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetModuleNameStringWide method [Windows Debugging], GetModuleNameStringWide method [Windows Debugging], IDebugSymbols3 interface, GetModuleNameStringWide,IDebugSymbols3.GetModuleNameStringWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetModuleNameStringWide method, IDebugSymbols3::GetModuleNameStringWide, dbgeng/IDebugSymbols3::GetModuleNameStringWide, debugger.getmodulenamestringwide
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
-	IDebugSymbols3.GetModuleNameStringWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetModuleNameStringWide method


## -description


The <b>GetModuleNameStringWide</b>  method returns the name of the specified module.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetModuleNameStringWide method%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

