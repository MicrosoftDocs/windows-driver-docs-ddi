---
UID: NF:dbgeng.IDebugRegisters2.GetValues2
title: IDebugRegisters2::GetValues2 method
author: windows-driver-content
description: The GetValues2 method fetches the value of several of the target's registers.
old-location: debugger\getvalues2.htm
old-project: debugger
ms.assetid: 182e55ec-1a99-4bd6-bcf6-d5e8302b9eae
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetValues2 method [Windows Debugging], GetValues2 method [Windows Debugging], IDebugRegisters2 interface, GetValues2,IDebugRegisters2.GetValues2, IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], GetValues2 method, IDebugRegisters2::GetValues2, IDebugRegisters_de7a1e67-5ffe-48f8-a19d-63858c500389.xml, dbgeng/IDebugRegisters2::GetValues2, debugger.getvalues2
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
req.lib: dbgeng.h
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
-	IDebugRegisters2.GetValues2
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugRegisters2::GetValues2 method


## -description


The <b>GetValues2</b> method fetches the value of several of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -syntax


````
HRESULT GetValues2(
  [in]           ULONG        Source,
  [in]           ULONG        Count,
  [in, optional] PULONG       Indices,
  [in]           ULONG        Start,
  [out]          PDEBUG_VALUE Values
);
````


## -parameters




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
 


### -param Count [in]

Specifies the number of registers whose values are requested.


### -param Indices [in, optional]

Specifies an array that contains the indices of the registers from which to get the values.  The number of elements in this array is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used instead.


### -param Start [in]

If <i>Indices</i> is <b>NULL</b>, the registers will be read consecutively starting at this index.  Otherwise, it is ignored.


### -param Values [out]

Receives the values of the registers.  The number of elements that this array holds is <i>Count</i>.  See <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> for a description of this parameter type.


## -returns



This list does not contain all the erros that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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
The value of the index of one of the registers is greater than the number of registers on the target computer.  Partial results might have been obtained; those registers that could not be read will have the type DEBUG_VALUE_INVALID.

</td>
</tr>
</table>
 




## -remarks



If the return value is not S_OK, some of the registers still might have been read.  If the target was not accessible, the return type is E_UNEXPECTED and <i>Values</i> is unchanged. Otherwise, <i>Values</i> will contain partial results and the registers that could not be read will have type DEBUG_VALUE_INVALID.  Ambiguity in the case of the return value E_UNEXPECTED can be avoided by setting the memory of <i>Values</i> to zero before calling this method.

The method <a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a>



<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff597624">GetValue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::GetValues2 method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

