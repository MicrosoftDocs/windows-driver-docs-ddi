---
UID: NF:dbgeng.IDebugSymbols.GetModuleParameters
title: IDebugSymbols::GetModuleParameters method
author: windows-driver-content
description: The GetModuleParameters method returns parameters for modules in the target.
old-location: debugger\getmoduleparameters.htm
old-project: debugger
ms.assetid: f744cd2e-a4ec-43be-a5cc-9135a73bce80
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetModuleParameters method [Windows Debugging], GetModuleParameters method [Windows Debugging], IDebugSymbols interface, GetModuleParameters method [Windows Debugging], IDebugSymbols2 interface, GetModuleParameters method [Windows Debugging], IDebugSymbols3 interface, GetModuleParameters,IDebugSymbols.GetModuleParameters, IDebugSymbols, IDebugSymbols interface [Windows Debugging], GetModuleParameters method, IDebugSymbols2 interface [Windows Debugging], GetModuleParameters method, IDebugSymbols2::GetModuleParameters, IDebugSymbols3 interface [Windows Debugging], GetModuleParameters method, IDebugSymbols3::GetModuleParameters, IDebugSymbols::GetModuleParameters, IDebugSymbols_0a78fd64-15b7-4032-83a8-9867037e5081.xml, dbgeng/IDebugSymbols2::GetModuleParameters, dbgeng/IDebugSymbols3::GetModuleParameters, dbgeng/IDebugSymbols::GetModuleParameters, debugger.getmoduleparameters
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
-	IDebugSymbols.GetModuleParameters
-	IDebugSymbols2.GetModuleParameters
-	IDebugSymbols3.GetModuleParameters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols::GetModuleParameters method


## -description


The <b>GetModuleParameters</b> method returns parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">modules</a> in the target.


## -parameters




### -param Count [in]

Specifies the number of modules whose parameters are desired.


### -param Bases [in, optional]

Specifies an array of locations in the target's virtual address space representing the base address of the modules whose parameters are desired.  The size of this array is the value of <i>Count</i>.  If <i>Bases</i> is <b>NULL</b>, the <i>Start</i> parameter is used to specify the modules by index.


### -param Start [in]

Specifies the index of the first module whose parameters are desired.  If <i>Bases</i> is not <b>NULL</b>, this parameter is ignored.


### -param Params [out]

Receives the parameters.  The size of this array is the value of <i>Count</i>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541514">DEBUG_MODULE_PARAMETERS</a>.


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



In the cases when partial results are returned, the entries in the array <i>Params</i> corresponding to modules that could not be found have their <b>Base</b> field set to DEBUG_INVALID_OFFSET.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541514">DEBUG_MODULE_PARAMETERS</a>.

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541514">DEBUG_MODULE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

