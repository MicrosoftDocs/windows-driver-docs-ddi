---
UID: NF:dbgeng.IDebugRegisters2.OutputRegisters
title: IDebugRegisters2::OutputRegisters method
author: windows-driver-content
description: The OutputRegisters method formats and sends the target's registers to the clients as output.
old-location: debugger\outputregisters.htm
old-project: debugger
ms.assetid: d1354ab7-4d7d-4cc2-8e30-763d8b881a11
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugRegisters interface [Windows Debugging], OutputRegisters method, IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], OutputRegisters method, IDebugRegisters2::OutputRegisters, IDebugRegisters::OutputRegisters, IDebugRegisters_65d62961-afc5-4609-86d2-c55757fe6ce1.xml, OutputRegisters method [Windows Debugging], OutputRegisters method [Windows Debugging], IDebugRegisters interface, OutputRegisters method [Windows Debugging], IDebugRegisters2 interface, OutputRegisters,IDebugRegisters2.OutputRegisters, dbgeng/IDebugRegisters2::OutputRegisters, dbgeng/IDebugRegisters::OutputRegisters, debugger.outputregisters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	IDebugRegisters.OutputRegisters
-	IDebugRegisters2.OutputRegisters
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters2::OutputRegisters method


## -description


The <b>OutputRegisters</b> method formats and sends the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a> to the clients as output.


## -syntax


````
HRESULT OutputRegisters(
  [in] ULONG OutputControl,
  [in] ULONG Flags
);
````


## -parameters




### -param OutputControl [in]

Specifies which clients should be sent the output of the formatted registers.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a> for possible values.


### -param Flags [in]

Specifies which set of registers to print.  This can either be DEBUG_REGISTERS_DEFAULT to print commonly used registers, DEBUG_REGISTERS_ALL to print all the sets of registers, or a combination of the values listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_REGISTERS_INT32

</td>
<td>
Print the 32-bit register set.

</td>
</tr>
<tr>
<td>
DEBUG_REGISTERS_INT64

</td>
<td>
Print the 64-bit register set.

</td>
</tr>
<tr>
<td>
DEBUG_REGISTERS_FLOAT

</td>
<td>
Print the floating-point register set.

</td>
</tr>
</table>
 


## -returns



This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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



The registers are formatted in a way that is specific to the target architecture's register set.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff553245">OutputRegisters2</a> performs the same task as this method but also allows the register source to be specified.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.  For details on sending output to the clients, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>



<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553245">OutputRegisters2</a>



 

 


