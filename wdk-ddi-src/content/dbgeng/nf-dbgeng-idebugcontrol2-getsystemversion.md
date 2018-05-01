---
UID: NF:dbgeng.IDebugControl2.GetSystemVersion
title: IDebugControl2::GetSystemVersion
author: windows-driver-content
description: The GetSystemVersion method returns information that identifies the operating system on the computer that is running the current target.
old-location: debugger\getsystemversion.htm
old-project: debugger
ms.assetid: 9418ac12-3de0-4477-a725-437700c4d83c
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetSystemVersion, GetSystemVersion method [Windows Debugging], GetSystemVersion method [Windows Debugging],IDebugControl interface, GetSystemVersion method [Windows Debugging],IDebugControl2 interface, GetSystemVersion method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetSystemVersion method, IDebugControl2 interface [Windows Debugging],GetSystemVersion method, IDebugControl2.GetSystemVersion, IDebugControl2::GetSystemVersion, IDebugControl3 interface [Windows Debugging],GetSystemVersion method, IDebugControl3::GetSystemVersion, IDebugControl::GetSystemVersion, IDebugControl_92a4c34c-aa39-43e5-ad31-0ce26e45c246.xml, dbgeng/IDebugControl2::GetSystemVersion, dbgeng/IDebugControl3::GetSystemVersion, dbgeng/IDebugControl::GetSystemVersion, debugger.getsystemversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
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
-	IDebugControl.GetSystemVersion
-	IDebugControl2.GetSystemVersion
-	IDebugControl3.GetSystemVersion
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugControl2::GetSystemVersion


## -description


The <b>GetSystemVersion</b> method returns information that identifies the operating system on the computer that is running the current target.


## -parameters




### -param PlatformId [out]

Receives the platform ID. <i>PlatformId</i> is always VER_PLATFORM_WIN32_NT for NT-based Windows.   


### -param Major [out]

Receives 0xF if the target's operating system is a <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">free build</a>, or 0xC if the operating system is a <a href="https://msdn.microsoft.com/ac439eb8-b491-4215-877d-5ee177fbdb39">checked build</a>.


### -param Minor [out]

Receives the build number for the target's operating system.


### -param ServicePackString [out, optional]

Receives the string for the service pack level of the target computer.  If <i>ServicePackString</i> is <b>NULL</b>, this information is not returned.  If no service pack is installed, <i>ServicePackString</i> can be empty.


### -param ServicePackStringSize [in]

Specifies the size, in characters, of the buffer that <i>ServicePackString</i> specifies.


### -param ServicePackStringUsed [out, optional]

Receives the size, in characters, of the string of the service pack level.  If <i>ServicePackStringUsed</i> is <b>NULL</b>, this information is not returned.


### -param ServicePackNumber [out]

Receives the service pack level of the target's operating system.


### -param BuildString [out, optional]

Receives the string that identifies the build of the system.  If <i>BuildString</i> is <b>NULL</b>, this information is not returned.


### -param BuildStringSize [in]

Specifies the size, in characters, of the buffer that <i>BuildString</i> specifies.


### -param BuildStringUsed [out, optional]

Receives the size, in characters, of the string that identifies the build.  If <i>BuildStringUsed</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the <i>ServicePackString</i> buffer or the <i>BuildString</i> buffer were too small and the corresponding string was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549245">GetSystemVersionString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549258">GetSystemVersionValues</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

