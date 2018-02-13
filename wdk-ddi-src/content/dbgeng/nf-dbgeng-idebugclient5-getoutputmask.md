---
UID: NF:dbgeng.IDebugClient5.GetOutputMask
title: IDebugClient5::GetOutputMask method
author: windows-driver-content
description: The GetOutputMask method returns the output mask currently set for the client.
old-location: debugger\getoutputmask.htm
old-project: debugger
ms.assetid: b1076b17-9175-4823-abb7-1c864670e8d5
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugClient2::GetOutputMask, IDebugClient5::GetOutputMask, dbgeng/IDebugClient4::GetOutputMask, IDebugClient5, GetOutputMask method [Windows Debugging], IDebugClient3 interface, IDebugClient3 interface [Windows Debugging], GetOutputMask method, dbgeng/IDebugClient5::GetOutputMask, IDebugClient4 interface [Windows Debugging], GetOutputMask method, GetOutputMask method [Windows Debugging], IDebugClient5 interface, dbgeng/IDebugClient2::GetOutputMask, IDebugClient3::GetOutputMask, dbgeng/IDebugClient::GetOutputMask, IDebugClient2, GetOutputMask method [Windows Debugging], IDebugClient2 interface, IDebugClient5 interface [Windows Debugging], GetOutputMask method, GetOutputMask method [Windows Debugging], IDebugClient4, IDebugClient_ff2626fe-2299-4008-b655-0b7dbd46ef8b.xml, GetOutputMask method [Windows Debugging], IDebugClient interface, IDebugClient3, IDebugClient, debugger.getoutputmask, dbgeng/IDebugClient3::GetOutputMask, IDebugClient interface [Windows Debugging], GetOutputMask method, GetOutputMask, IDebugClient4::GetOutputMask, IDebugClient2 interface [Windows Debugging], GetOutputMask method, IDebugClient::GetOutputMask, GetOutputMask method [Windows Debugging], IDebugClient4 interface
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
-	IDebugClient.GetOutputMask
-	IDebugClient2.GetOutputMask
-	IDebugClient3.GetOutputMask
-	IDebugClient4.GetOutputMask
-	IDebugClient5.GetOutputMask
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient5::GetOutputMask method


## -description


The <b>GetOutputMask</b> method returns the output mask currently set for the client.


## -syntax


````
HRESULT GetOutputMask(
  [out] PULONG Mask
);
````


## -parameters




### -param Mask [out]

Receives the output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for details on how to interpret this value.


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



For an overview of output in the debugger engine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::GetOutputMask method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

