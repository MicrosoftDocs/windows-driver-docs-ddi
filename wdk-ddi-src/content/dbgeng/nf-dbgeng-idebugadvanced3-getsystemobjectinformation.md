---
UID: NF:dbgeng.IDebugAdvanced3.GetSystemObjectInformation
title: IDebugAdvanced3::GetSystemObjectInformation method
author: windows-driver-content
description: The GetSystemObjectInformation method returns information about operating system objects on the target.
old-location: debugger\getsystemobjectinformation.htm
old-project: debugger
ms.assetid: 7e95a16e-e62d-49df-9889-fab0a85f9cbc
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetSystemObjectInformation method [Windows Debugging], IDebugAdvanced2 interface, IDebugAdvanced3 interface [Windows Debugging], GetSystemObjectInformation method, GetSystemObjectInformation method [Windows Debugging], dbgeng/IDebugAdvanced3::GetSystemObjectInformation, IDebugAdvanced2, IDebugAdvanced2 interface [Windows Debugging], GetSystemObjectInformation method, IDebugAdvanced2::GetSystemObjectInformation, GetSystemObjectInformation, GetSystemObjectInformation method [Windows Debugging], IDebugAdvanced3 interface, IDebugAdvanced_a1f6b5cc-0b56-417f-b515-45c999499ba7.xml, debugger.getsystemobjectinformation, IDebugAdvanced3::GetSystemObjectInformation, dbgeng/IDebugAdvanced2::GetSystemObjectInformation, IDebugAdvanced3
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
-	IDebugAdvanced2.GetSystemObjectInformation
-	IDebugAdvanced3.GetSystemObjectInformation
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugAdvanced3::GetSystemObjectInformation method


## -description


The <b>GetSystemObjectInformation</b> method returns information about operating system objects on the target.


## -syntax


````
HRESULT GetSystemObjectInformation(
  [in]            ULONG   Which,
  [in]            ULONG64 Arg64,
  [in]            ULONG   Arg32,
  [out, optional] PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  InfoSize
);
````


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

<a href="..\dbgeng\ns-dbgeng-_debug_thread_basic_information.md">DEBUG_THREAD_BASIC_INFORMATION</a>


</td>
</tr>
</table>
 


### -param BufferSize [in]

Specifies the size, in bytes, of the buffer <i>Buffer</i>.


### -param InfoSize [out, optional]

Receives the size of the information that is returned.


##### - Arg64.DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

Not used.


##### - Arg32.DEBUG_SYSOBJINFO_THREAD_BASIC_INFORMATION

The engine thread ID of the desired thread.


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

<a href="..\dbgeng\nn-dbgeng-idebugadvanced3.md">IDebugAdvanced3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects.md">IDebugSystemObjects</a>



<a href="..\dbgeng\nn-dbgeng-idebugadvanced2.md">IDebugAdvanced2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced2::GetSystemObjectInformation method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

