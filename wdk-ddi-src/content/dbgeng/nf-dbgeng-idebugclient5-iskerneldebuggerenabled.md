---
UID: NF:dbgeng.IDebugClient5.IsKernelDebuggerEnabled
title: IDebugClient5::IsKernelDebuggerEnabled method
author: windows-driver-content
description: The IsKernelDebuggerEnabled method checks whether kernel debugging is enabled for the local kernel.
old-location: debugger\iskerneldebuggerenabled.htm
old-project: Debugger
ms.assetid: a6dc4832-6b9b-441e-a57a-6fcb2cafa2c6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient4, IDebugClient5, IDebugClient3::IsKernelDebuggerEnabled, IDebugClient_05c5446d-28b4-4d9b-bb20-7dc1746545d6.xml, debugger.iskerneldebuggerenabled, IsKernelDebuggerEnabled method [Windows Debugging], IDebugClient4 interface, IsKernelDebuggerEnabled method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient3::IsKernelDebuggerEnabled, dbgeng/IDebugClient2::IsKernelDebuggerEnabled, IsKernelDebuggerEnabled method [Windows Debugging], IDebugClient3 interface, dbgeng/IDebugClient4::IsKernelDebuggerEnabled, IDebugClient3 interface [Windows Debugging], IsKernelDebuggerEnabled method, IsKernelDebuggerEnabled method [Windows Debugging], dbgeng/IDebugClient5::IsKernelDebuggerEnabled, IDebugClient2 interface [Windows Debugging], IsKernelDebuggerEnabled method, IsKernelDebuggerEnabled, IDebugClient5 interface [Windows Debugging], IsKernelDebuggerEnabled method, IDebugClient5::IsKernelDebuggerEnabled, IDebugClient2, IDebugClient2::IsKernelDebuggerEnabled, IsKernelDebuggerEnabled method [Windows Debugging], IDebugClient2 interface, IDebugClient4::IsKernelDebuggerEnabled, IDebugClient4 interface [Windows Debugging], IsKernelDebuggerEnabled method, IDebugClient3
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
-	IDebugClient2.IsKernelDebuggerEnabled
-	IDebugClient3.IsKernelDebuggerEnabled
-	IDebugClient4.IsKernelDebuggerEnabled
-	IDebugClient5.IsKernelDebuggerEnabled
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::IsKernelDebuggerEnabled method


## -description


The <b>IsKernelDebuggerEnabled</b> method checks whether kernel debugging is enabled for the local kernel.


## -syntax


````
HRESULT IsKernelDebuggerEnabled();
````


## -parameters






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
Kernel debugging is enabled for the local kernel.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
Kernel debugging is not enabled for the local kernel.

</td>
</tr>
</table>
 




## -remarks



Kernel debugging is available for the local computer if the computer was booted by using the <b>/debug</b> boot switch.  In some Windows installations, <a href="https://msdn.microsoft.com/0dc78f83-a695-4b2c-a5cd-d7f365a9560f">local kernel debugging</a> is supported when other switches--such as <b>/debugport</b>--are used, but this is not a guaranteed feature of Windows and should not be relied on.  For more information about kernel debugging on a single computer, see <a href="https://msdn.microsoft.com/e66dc23b-9254-4148-9828-d27c30bfa492">Performing Local Kernel Debugging</a>.

For more information about connecting to live kernel-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552005">Live Kernel-Mode Targets</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538145">AttachKernel</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient2::IsKernelDebuggerEnabled method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

