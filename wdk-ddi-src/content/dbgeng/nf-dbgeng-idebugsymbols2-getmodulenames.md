---
UID: NF:dbgeng.IDebugSymbols2.GetModuleNames
title: IDebugSymbols2::GetModuleNames method
author: windows-driver-content
description: The GetModuleNames method returns the names of the specified module.
old-location: debugger\getmodulenames.htm
old-project: debugger
ms.assetid: dd33f88a-91f6-4ea4-bb6b-6fb505676684
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetModuleNames method [Windows Debugging], GetModuleNames method [Windows Debugging], IDebugSymbols interface, GetModuleNames method [Windows Debugging], IDebugSymbols2 interface, GetModuleNames method [Windows Debugging], IDebugSymbols3 interface, GetModuleNames,IDebugSymbols2.GetModuleNames, IDebugSymbols interface [Windows Debugging], GetModuleNames method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], GetModuleNames method, IDebugSymbols2::GetModuleNames, IDebugSymbols3 interface [Windows Debugging], GetModuleNames method, IDebugSymbols3::GetModuleNames, IDebugSymbols::GetModuleNames, IDebugSymbols_b200104b-e0e6-4470-80f9-d6904c346737.xml, dbgeng/IDebugSymbols2::GetModuleNames, dbgeng/IDebugSymbols3::GetModuleNames, dbgeng/IDebugSymbols::GetModuleNames, debugger.getmodulenames
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
-	IDebugSymbols.GetModuleNames
-	IDebugSymbols2.GetModuleNames
-	IDebugSymbols3.GetModuleNames
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::GetModuleNames method


## -description


The <b>GetModuleNames</b> method returns the names of the specified module.


## -parameters




### -param Index [in]

Specifies the index of the module whose names are requested.  If it is set to DEBUG_ANY_ID, the module is specified by <i>Base</i>.


### -param Base [in]

Specifies the base address of the module whose names are requested.  This parameter is only used if <i>Index</i> is set to DEBUG_ANY_ID.


### -param ImageNameBuffer [out, optional]

Receives the image name of the module.  If <i>ImageNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param ImageNameBufferSize [in]

Specifies the size in characters of the buffer <i>ImageNameBuffer</i> in characters.


### -param ImageNameSize [out, optional]

Receives the size in characters of the image name.  If <i>ImageNameSize</i> is <b>NULL</b>, this information is not returned.


### -param ModuleNameBuffer [out, optional]

Receives the module name of the module.  If <i>ModuleNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param ModuleNameBufferSize [in]

Specifies the size in characters of the buffer <i>ModuleNameBuffer</i>.


### -param ModuleNameSize [out, optional]

Receives the size in characters of the module name.  If <i>ModuleNameSize</i> is <b>NULL</b>, this information is not returned.


### -param LoadedImageNameBuffer [out, optional]

Receives the loaded image name of the module.  If <i>LoadedImageNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param LoadedImageNameBufferSize [in]

Specifies the size in characters of the buffer <i>LoadedImageNameBuffer</i>.


### -param LoadedImageNameSize [out, optional]

Receives the size in characters of the loaded image name.  If <i>LoadedImageNameSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547149">GetModuleNameString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetModuleNames method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

