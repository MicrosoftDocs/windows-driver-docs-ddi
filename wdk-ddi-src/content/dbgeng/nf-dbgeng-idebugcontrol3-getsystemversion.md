---
UID: NF:dbgeng.IDebugControl3.GetSystemVersion
title: IDebugControl3::GetSystemVersion method
author: windows-driver-content
description: The GetSystemVersion method returns information that identifies the operating system on the computer that is running the current target.
old-location: debugger\getsystemversion.htm
old-project: debugger
ms.assetid: 9418ac12-3de0-4477-a725-437700c4d83c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetSystemVersion, GetSystemVersion
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
req.alt-api: IDebugControl.GetSystemVersion,IDebugControl2.GetSystemVersion,IDebugControl3.GetSystemVersion
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::GetSystemVersion method



## -description
The <b>GetSystemVersion</b> method returns information that identifies the operating system on the computer that is running the current target.



## -syntax

````
HRESULT GetSystemVersion(
  [out]           PULONG PlatformId,
  [out]           PULONG Major,
  [out]           PULONG Minor,
  [out, optional] PSTR   ServicePackString,
  [in]            ULONG  ServicePackStringSize,
  [out, optional] PULONG ServicePackStringUsed,
  [out]           PULONG ServicePackNumber,
  [out, optional] PSTR   BuildString,
  [in]            ULONG  BuildStringSize,
  [out, optional] PULONG BuildStringUsed
);
````


## -parameters

### -param PlatformId [out]

Receives the platform ID. <i>PlatformId</i> is always VER_PLATFORM_WIN32_NT for NT-based Windows.   


### -param Major [out]

Receives 0xF if the target's operating system is a <a href="wdkgloss.f#wdkgloss.free_build#wdkgloss.free_build"><i>free build</i></a>, or 0xC if the operating system is a <a href="wdkgloss.c#wdkgloss.checked_build#wdkgloss.checked_build"><i>checked build</i></a>.


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the <i>ServicePackString</i> buffer or the <i>BuildString</i> buffer were too small and the corresponding string was truncated.

 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549245">GetSystemVersionString</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549258">GetSystemVersionValues</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetSystemVersion method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

