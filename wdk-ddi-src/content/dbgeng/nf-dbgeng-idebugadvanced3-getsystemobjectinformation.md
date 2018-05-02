---
UID: NF:dbgeng.IDebugAdvanced3.GetSystemObjectInformation
title: IDebugAdvanced3::GetSystemObjectInformation
author: windows-driver-content
description: The GetSystemObjectInformation method returns information about operating system objects on the target.
old-location: debugger\getsystemobjectinformation.htm
old-project: debugger
ms.assetid: 7e95a16e-e62d-49df-9889-fab0a85f9cbc
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetSystemObjectInformation, GetSystemObjectInformation method [Windows Debugging], GetSystemObjectInformation method [Windows Debugging],IDebugAdvanced2 interface, GetSystemObjectInformation method [Windows Debugging],IDebugAdvanced3 interface, IDebugAdvanced2 interface [Windows Debugging],GetSystemObjectInformation method, IDebugAdvanced2::GetSystemObjectInformation, IDebugAdvanced3 interface [Windows Debugging],GetSystemObjectInformation method, IDebugAdvanced3.GetSystemObjectInformation, IDebugAdvanced3::GetSystemObjectInformation, IDebugAdvanced_a1f6b5cc-0b56-417f-b515-45c999499ba7.xml, dbgeng/IDebugAdvanced2::GetSystemObjectInformation, dbgeng/IDebugAdvanced3::GetSystemObjectInformation, debugger.getsystemobjectinformation
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
-	IDebugAdvanced2.GetSystemObjectInformation
-	IDebugAdvanced3.GetSystemObjectInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugAdvanced3::GetSystemObjectInformation


## -description


The <b>GetSystemObjectInformation</b> method returns information about operating system objects on the target.


## -parameters




### -param Which [in]

Specifies the type of object and the type of information to return about that object.  <i>Which</i> can take the following value.

<table>
<tr>
<th>Value</th>
<th>Information returned</th>
</tr>
<tr>
<td>
DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

</td>
<td>
Returns details of the thread specified by engine thread ID.

</td>
</tr>
</table>
 


### -param Arg64 [in]

Specifies a 64-bit argument.  This parameter has the following interpretations depending on the value of <i>Which</i>:





#### DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

Not used.


### -param Arg32 [in]

Specifies a 32-bit argument.  This parameter has the following interpretations depending on the value of <i>Which</i>:





#### DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

The engine thread ID of the desired thread.


### -param Buffer [out, optional]

Receives the requested information.  The type of data returned in <i>Buffer</i> depends on the value of <i>Which</i>.

<table>
<tr>
<th>Value</th>
<th>Return type</th>
</tr>
<tr>
<td>
DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541695">DEBUG_THREAD_BASIC_INFORMATION</a>


</td>
</tr>
</table>
 


### -param BufferSize [in]

Specifies the size, in bytes, of the buffer <i>Buffer</i>.


### -param InfoSize [out, optional]

Receives the size of the information that is returned.


##### - Arg32.DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

The engine thread ID of the desired thread.


##### - Arg64.DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

Not used.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the information would not fit in the buffer <i>Buffer</i>, so the information was truncated.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549803">IDebugAdvanced2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549807">IDebugAdvanced3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550875">IDebugSystemObjects</a>
 

 

