---
UID: NF:dbgeng.IDebugSymbols2.GetModuleParameters
title: IDebugSymbols2::GetModuleParameters method
author: windows-driver-content
description: The GetModuleParameters method returns parameters for modules in the target.
old-location: debugger\getmoduleparameters.htm
old-project: debugger
ms.assetid: f744cd2e-a4ec-43be-a5cc-9135a73bce80
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDebugSymbols2::GetModuleParameters, dbgeng/IDebugSymbols2::GetModuleParameters, GetModuleParameters method [Windows Debugging], IDebugSymbols2, GetModuleParameters method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols_0a78fd64-15b7-4032-83a8-9867037e5081.xml, IDebugSymbols2 interface [Windows Debugging], GetModuleParameters method, IDebugSymbols interface [Windows Debugging], GetModuleParameters method, GetModuleParameters method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols, dbgeng/IDebugSymbols::GetModuleParameters, GetModuleParameters method [Windows Debugging], IDebugSymbols interface, IDebugSymbols::GetModuleParameters, IDebugSymbols3::GetModuleParameters, debugger.getmoduleparameters, dbgeng/IDebugSymbols3::GetModuleParameters, GetModuleParameters, IDebugSymbols3 interface [Windows Debugging], GetModuleParameters method
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
-	IDebugSymbols.GetModuleParameters
-	IDebugSymbols2.GetModuleParameters
-	IDebugSymbols3.GetModuleParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::GetModuleParameters method


## -description


The <b>GetModuleParameters</b> method returns parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> in the target.


## -syntax


````
HRESULT GetModuleParameters(
  [in]           ULONG                    Count,
  [in, optional] PULONG64                 Bases,
  [in]           ULONG                    Start,
  [out]          PDEBUG_MODULE_PARAMETERS Params
);
````


## -parameters




### -param Count [in]

Specifies the number of modules whose parameters are desired.


### -param Bases [in, optional]

Specifies an array of locations in the target's virtual address space representing the base address of the modules whose parameters are desired.  The size of this array is the value of <i>Count</i>.  If <i>Bases</i> is <b>NULL</b>, the <i>Start</i> parameter is used to specify the modules by index.


### -param Start [in]

Specifies the index of the first module whose parameters are desired.  If <i>Bases</i> is not <b>NULL</b>, this parameter is ignored.


### -param Params [out]

Receives the parameters.  The size of this array is the value of <i>Count</i>.  See <a href="..\dbgeng\ns-dbgeng-_debug_module_parameters.md">DEBUG_MODULE_PARAMETERS</a>.


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
The method was successful.  However, if <i>Bases</i> is not <b>NULL</b>, it is possible that not all of the modules were found, in which case partial results are returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
When <i>Bases</i> is <b>NULL</b>, this value indicates that the target contains fewer than the sum of <i>Count</i> and <i>Start</i> modules.  Partial results are returned.

</td>
</tr>
</table>
 




## -remarks



In the cases when partial results are returned, the entries in the array <i>Params</i> corresponding to modules that could not be found have their <b>Base</b> field set to DEBUG_INVALID_OFFSET.  See <a href="..\dbgeng\ns-dbgeng-_debug_module_parameters.md">DEBUG_MODULE_PARAMETERS</a>.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also

<a href="..\dbgeng\ns-dbgeng-_debug_module_parameters.md">DEBUG_MODULE_PARAMETERS</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetModuleParameters method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

