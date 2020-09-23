---
UID: NF:dbgeng.IDebugControl4.GetSystemVersionValues
title: IDebugControl4::GetSystemVersionValues (dbgeng.h)
description: The GetSystemVersionValues method returns version number information for the current target.
old-location: debugger\getsystemversionvalues.htm
tech.root: debugger
ms.assetid: 77996a5f-aaf0-4c8c-9d29-498612ae9c0d
ms.date: 05/03/2018
keywords: ["IDebugControl4::GetSystemVersionValues"]
ms.keywords: GetSystemVersionValues, GetSystemVersionValues method [Windows Debugging], GetSystemVersionValues method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetSystemVersionValues method, IDebugControl4.GetSystemVersionValues, IDebugControl4::GetSystemVersionValues, IDebugControl_32de1433-8721-41c0-9b14-43ef8f7bcf70.xml, dbgeng/IDebugControl4::GetSystemVersionValues, debugger.getsystemversionvalues
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl4::GetSystemVersionValues
 - dbgeng/IDebugControl4::GetSystemVersionValues
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl4.GetSystemVersionValues
---

# IDebugControl4::GetSystemVersionValues


## -description

The <b>GetSystemVersionValues</b> method returns version number information for the current target.

## -parameters

### -param PlatformId 

[out]
Receives the platform ID. <i>PlatformId</i> is always VER_PLATFORM_WIN32_NT for NT-based Windows.

### -param Win32Major 

[out]
Receives the major version number of the target's operating system.  For Windows 2000, Windows XP, and Windows Server 2003, this number is 5.  For Windows Vista, Windows 7, and Windows 8, this number is 6.

### -param Win32Minor 

[out]
Receives the minor version number for the target's operating system.  For Windows 2000 this is 0; for Windows XP, 1; for Windows Server 2003, 2.  For Windows Vista, this is 0; for Windows 7, 1; for Windows 8, 2.

### -param KdMajor 

[out, optional]
Receives 0xF if the target's operating system is a free build, and 0xC if it is a checked build.

### -param KdMinor 

[out, optional]
Receives the build number for the target's operating system.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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

For more information, see <a href="/windows-hardware/drivers/debugger/target-information">Target Information</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getsystemversion">GetSystemVersion</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol4-getsystemversionstring">GetSystemVersionString</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>