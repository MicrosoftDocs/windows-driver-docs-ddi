---
UID: NF:dbgeng.IDebugControl4.GetSystemVersionValues
title: IDebugControl4::GetSystemVersionValues method
author: windows-driver-content
description: The GetSystemVersionValues method returns version number information for the current target.
old-location: debugger\getsystemversionvalues.htm
old-project: debugger
ms.assetid: 77996a5f-aaf0-4c8c-9d29-498612ae9c0d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSystemVersionValues method [Windows Debugging], IDebugControl4 interface [Windows Debugging], GetSystemVersionValues method, debugger.getsystemversionvalues, dbgeng/IDebugControl4::GetSystemVersionValues, IDebugControl_32de1433-8721-41c0-9b14-43ef8f7bcf70.xml, IDebugControl4, GetSystemVersionValues method [Windows Debugging], IDebugControl4 interface, GetSystemVersionValues, IDebugControl4::GetSystemVersionValues
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
-	IDebugControl4.GetSystemVersionValues
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugControl4::GetSystemVersionValues method


## -description


The <b>GetSystemVersionValues</b> method returns version number information for the current target.


## -syntax


````
HRESULT GetSystemVersionValues(
  [out]           PULONG PlatformId,
  [out]           PULONG Win32Major,
  [out]           PULONG Win32Minor,
  [out, optional] PULONG KdMajor,
  [out, optional] PULONG KdMinor
);
````


## -parameters




### -param PlatformId [out]

Receives the platform ID. <i>PlatformId</i> is always VER_PLATFORM_WIN32_NT for NT-based Windows.   


### -param Win32Major [out]

Receives the major version number of the target's operating system.  For Windows 2000, Windows XP, and Windows Server 2003, this number is 5.  For Windows Vista, Windows 7, and Windows 8, this number is 6.


### -param Win32Minor [out]

Receives the minor version number for the target's operating system.  For Windows 2000 this is 0; for Windows XP, 1; for Windows Server 2003, 2.  For Windows Vista, this is 0; for Windows 7, 1; for Windows 8, 2.


### -param KdMajor [out, optional]

Receives 0xF if the target's operating system is a free build, and 0xC if it is a checked build.


### -param KdMinor [out, optional]

Receives the build number for the target's operating system.


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


For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549245">GetSystemVersionString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549234">GetSystemVersion</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetSystemVersionValues method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

