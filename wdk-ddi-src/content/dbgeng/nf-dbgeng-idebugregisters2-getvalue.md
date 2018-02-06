---
UID: NF:dbgeng.IDebugRegisters2.GetValue
title: IDebugRegisters2::GetValue method
author: windows-driver-content
description: The GetValue method gets the value of one of the target's registers.
old-location: debugger\getvalue.htm
old-project: debugger
ms.assetid: 227d7b4f-bf94-4763-bb1f-32efbc087bb1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetValue method [Windows Debugging], GetValue, GetValue method [Windows Debugging], IDebugRegisters2 interface, IDebugRegisters_f3e89ca1-7516-476e-8c85-560d8f28f0a8.xml, IDebugRegisters::GetValue, IDebugRegisters interface [Windows Debugging], GetValue method, IDebugRegisters2, GetValue method [Windows Debugging], IDebugRegisters interface, IDebugRegisters2::GetValue, dbgeng/IDebugRegisters2::GetValue, IDebugRegisters2 interface [Windows Debugging], GetValue method, dbgeng/IDebugRegisters::GetValue, debugger.getvalue
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
-	IDebugRegisters.GetValue
-	IDebugRegisters2.GetValue
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugRegisters2::GetValue method


## -description


The <b>GetValue</b> method gets the value of one of the target's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">registers</a>.


## -syntax


````
HRESULT GetValue(
  [in]  ULONG        Register,
  [out] PDEBUG_VALUE Value
);
````


## -parameters




### -param Register [in]

Specifies the index of the register whose value is requested.


### -param Value [out]

Receives the value of the register.  See <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> for a description of this parameter type.


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
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
The target is not accessible, or the register could not be accessed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of Register is greater than the number of registers on the target machine.

</td>
</tr>
</table> 



## -remarks


To receive the values of multiple registers, use the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a> method instead.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549487">GetValues2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549480">GetValues</a>

<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>

<a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters::GetValue method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

