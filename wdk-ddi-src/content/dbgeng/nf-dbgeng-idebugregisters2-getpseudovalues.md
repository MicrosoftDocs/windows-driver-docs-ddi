---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoValues
title: IDebugRegisters2::GetPseudoValues method
author: windows-driver-content
description: The GetPseudoValues method returns the values of a number of pseudo-registers.
old-location: debugger\getpseudovalues.htm
old-project: debugger
ms.assetid: a1ad3b45-c89c-4990-a47b-20e47c05892a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetPseudoValues method [Windows Debugging], IDebugRegisters_56a9ae8d-1ef7-4b28-bcad-e9f7025aba4f.xml, debugger.getpseudovalues, GetPseudoValues method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters2::GetPseudoValues, IDebugRegisters2 interface [Windows Debugging], GetPseudoValues method, dbgeng/IDebugRegisters2::GetPseudoValues, GetPseudoValues, IDebugRegisters2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugRegisters2.GetPseudoValues
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugRegisters2::GetPseudoValues method


## -description


The <b>GetPseudoValues</b> method returns the values of a number of pseudo-registers.


## -syntax


````
HRESULT GetPseudoValues(
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

Specifies the number of pseudo-registers whose values are being requested.


### -param Indices [in, optional]

Specifies an array of indices of pseudo-registers whose values will be returned.  The size of <i>Indices</i> is <i>Count</i>.  If <i>Indices</i> is <b>NULL</b>, <i>Start</i> is used to specify the indices instead.


### -param Start [in]

Specifies the index of the first pseudo-register whose value will be returned.  The pseudo-registers, with indices between <i>Start</i> and <i>Start</i> plus <i>Count</i> minus one, will be returned.  <i>Start</i> is only used if <i>Indices</i> is <b>NULL</b>.


### -param Values [out]

Receives the values of the specified pseudo-registers.  The number of elements that this array holds is <i>Count</i>.  See <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> for a description of this parameter type.


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


For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556767">SetPseudoValues</a>

<a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a>

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::GetPseudoValues method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

