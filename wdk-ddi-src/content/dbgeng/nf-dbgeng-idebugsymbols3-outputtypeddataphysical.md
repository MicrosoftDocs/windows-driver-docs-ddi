---
UID: NF:dbgeng.IDebugSymbols3.OutputTypedDataPhysical
title: IDebugSymbols3::OutputTypedDataPhysical method
author: windows-driver-content
description: The OutputTypedDataPhysical method formats the contents of a variable in the target computer's physical memory, and then sends this to the output callbacks.
old-location: debugger\outputtypeddataphysical.htm
old-project: debugger
ms.assetid: 0c2ae1ff-bbf1-462f-b9ab-49f74cf12fae
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols interface [Windows Debugging], OutputTypedDataPhysical method, IDebugSymbols2 interface [Windows Debugging], OutputTypedDataPhysical method, IDebugSymbols2::OutputTypedDataPhysical, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], OutputTypedDataPhysical method, IDebugSymbols3::OutputTypedDataPhysical, IDebugSymbols::OutputTypedDataPhysical, IDebugSymbols_35ce4485-6c19-44fd-8382-011b0e620f48.xml, OutputTypedDataPhysical method [Windows Debugging], OutputTypedDataPhysical method [Windows Debugging], IDebugSymbols interface, OutputTypedDataPhysical method [Windows Debugging], IDebugSymbols2 interface, OutputTypedDataPhysical method [Windows Debugging], IDebugSymbols3 interface, OutputTypedDataPhysical,IDebugSymbols3.OutputTypedDataPhysical, dbgeng/IDebugSymbols2::OutputTypedDataPhysical, dbgeng/IDebugSymbols3::OutputTypedDataPhysical, dbgeng/IDebugSymbols::OutputTypedDataPhysical, debugger.outputtypeddataphysical
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
-	IDebugSymbols.OutputTypedDataPhysical
-	IDebugSymbols2.OutputTypedDataPhysical
-	IDebugSymbols3.OutputTypedDataPhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::OutputTypedDataPhysical method


## -description


The <b>OutputTypedDataPhysical</b> method formats the contents of a variable in the target computer's physical memory, and then sends this to the <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a>.


## -parameters




### -param OutputControl [in]

Specifies the output control used to determine which output callbacks can receive the output.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a> for possible values.


### -param Offset [in]

Specifies the physical address in the target computer's memory of the variable.


### -param Module [in]

Specifies the base address of the module containing the type of the variable.


### -param TypeId [in]

Specifies the type ID of the type of the variable.


### -param Flags [in]

Specifies the bit-set containing the formatting options.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541712">DEBUG_TYPEOPTS_XXX</a> for possible values.


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
</table>
 




## -remarks



This method is only available in kernel mode debugging.

The output produced by this method is the same as for the debugger command <b>DT</b>.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff542772">dt (Display Type)</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.



