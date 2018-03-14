---
UID: NF:dbgeng.IDebugRegisters2.OutputRegisters2
title: IDebugRegisters2::OutputRegisters2 method
author: windows-driver-content
description: The OutputRegisters2 method formats and outputs the target's registers.
old-location: debugger\outputregisters2.htm
old-project: debugger
ms.assetid: 444f7264-6072-4ee2-b3fd-030affa502b7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], OutputRegisters2 method, IDebugRegisters2::OutputRegisters2, IDebugRegisters_ecc2b40a-622b-4f1f-867b-2eb6b575559d.xml, OutputRegisters2 method [Windows Debugging], OutputRegisters2 method [Windows Debugging], IDebugRegisters2 interface, OutputRegisters2,IDebugRegisters2.OutputRegisters2, dbgeng/IDebugRegisters2::OutputRegisters2, debugger.outputregisters2
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
-	IDebugRegisters2.OutputRegisters2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters2::OutputRegisters2 method


## -description


The <b>OutputRegisters2</b> method formats and outputs the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -syntax


````
HRESULT OutputRegisters2(
  [in] ULONG OutputControl,
  [in] ULONG Source,
  [in] ULONG Flags
);
````


## -parameters




### -param OutputControl [in]

Specifies which clients should be sent the output of the formatted registers.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a> for possible values.


### -param Source [in]

Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://msdn.microsoft.com/3690903c-4281-4c65-98b0-00ca22206168">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context.

<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>
</td>
</tr>
</table>
 


### -param Flags [in]

Specifies which register sets to print.  This can either be DEBUG_REGISTERS_DEFAULT to print commonly used registers, DEBUG_REGISTERS_ALL to print all of the register sets, or a combination of the values listed in the following table.

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

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff553242">OutputRegisters</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553242">OutputRegisters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::OutputRegisters2 method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

