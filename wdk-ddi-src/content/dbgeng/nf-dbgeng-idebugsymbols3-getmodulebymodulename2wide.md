---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByModuleName2Wide
title: IDebugSymbols3::GetModuleByModuleName2Wide method
author: windows-driver-content
description: The GetModuleByModuleName2Wide method searches through the process's modules for one with the specified name.
old-location: debugger\getmodulebymodulename2wide.htm
old-project: debugger
ms.assetid: 49e27e24-d38a-4a22-a92f-33a384437250
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetModuleByModuleName2Wide method [Windows Debugging], GetModuleByModuleName2Wide method [Windows Debugging], IDebugSymbols3 interface, GetModuleByModuleName2Wide,IDebugSymbols3.GetModuleByModuleName2Wide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetModuleByModuleName2Wide method, IDebugSymbols3::GetModuleByModuleName2Wide, dbgeng/IDebugSymbols3::GetModuleByModuleName2Wide, debugger.getmodulebymodulename2wide
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
-	IDebugSymbols3.GetModuleByModuleName2Wide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetModuleByModuleName2Wide method


## -description


The <b>GetModuleByModuleName2Wide</b>  method searches through the process's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> for one with the specified name.


## -parameters




### -param Name [in]

Specifies the name of the desired module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Flags [in]

Specifies a bit-set containing options used when searching for the module with the specified name.  <i>Flags</i> may contain the following bit-flags:

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_LOADED_MODULES

</td>
<td>
Do not search the loaded modules.

</td>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_UNLOADED_MODULES

</td>
<td>
Do not search the unloaded modules.

</td>
</tr>
</table>
 


### -param Index [out, optional]

Receives the index of the first module with the name <i>Name</i>.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
One of the arguments passed in was invalid.

</td>
</tr>
</table>
 




## -remarks



Starting at the specified index, these methods return the first module they find with the specified name.  If the target has more than one module with this name, then subsequent modules can be found by repeated calls to these methods with higher values of <i>StartIndex</i>.  

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547095">GetModuleByModuleName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetModuleByModuleName2Wide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
