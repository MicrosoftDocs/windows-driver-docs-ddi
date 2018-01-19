---
UID: NF:dbgeng.IDebugControl4.GetLogFile2
title: IDebugControl4::GetLogFile2 method
author: windows-driver-content
description: The GetLogFile2 method returns the name of the currently open log file.
old-location: debugger\getlogfile2.htm
old-project: debugger
ms.assetid: 77ab08ce-96c5-4330-aab2-1bf4ab23cfc4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::GetLogFile2, GetLogFile2
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
req.alt-api: IDebugControl4.GetLogFile2
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

# IDebugControl4::GetLogFile2 method



## -description
The <b>GetLogFile2</b>  method returns the name of the currently open log file.



## -syntax

````
HRESULT GetLogFile2(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG FileSize,
  [out]           PULONG Flags
);
````


## -parameters

### -param Buffer [out, optional]

Receives the name of the currently open log file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FileSize [out, optional]

Receives the size, in characters, of the name of the log file.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Flags [out]

Receives the bit-flags that were used when opening the log file.  See the <i>Flags</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a> for a description of these flags.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful.  However, the name of the log file was too long to fit in the <i>Buffer</i> buffer so the name was truncated.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>There is no currently open log file.

 


## -remarks
For more information about log files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560116">Using Input and Output</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553155">OpenLogFile2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547016">GetLogFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539148">CloseLogFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547066">GetLogMask</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetLogFile2 method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

