---
UID: NF:dbgeng.IDebugClient4.GetOtherOutputMask
title: IDebugClient4::GetOtherOutputMask method
author: windows-driver-content
description: The GetOtherOutputMask method returns the output mask for another client.
old-location: debugger\getotheroutputmask.htm
old-project: Debugger
ms.assetid: b2334012-0aeb-43a2-aa5f-ecc51949ac46
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IDebugClient4, dbgeng/IDebugClient4::GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], IDebugClient4 interface, dbgeng/IDebugClient::GetOtherOutputMask, IDebugClient5 interface [Windows Debugging], GetOtherOutputMask method, IDebugClient4 interface [Windows Debugging], GetOtherOutputMask method, IDebugClient interface [Windows Debugging], GetOtherOutputMask method, dbgeng/IDebugClient5::GetOtherOutputMask, dbgeng/IDebugClient3::GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], IDebugClient5 interface, IDebugClient2::GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], IDebugClient3 interface, IDebugClient::GetOtherOutputMask, IDebugClient, debugger.getotheroutputmask, dbgeng/IDebugClient2::GetOtherOutputMask, IDebugClient3 interface [Windows Debugging], GetOtherOutputMask method, GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], IDebugClient interface, IDebugClient3::GetOtherOutputMask, IDebugClient4::GetOtherOutputMask, IDebugClient2 interface [Windows Debugging], GetOtherOutputMask method, IDebugClient2, GetOtherOutputMask method [Windows Debugging], IDebugClient2 interface, IDebugClient5::GetOtherOutputMask, GetOtherOutputMask method [Windows Debugging], IDebugClient3, IDebugClient_780a02ad-2f51-4142-a0d2-74220bf52623.xml
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
-	IDebugClient.GetOtherOutputMask
-	IDebugClient2.GetOtherOutputMask
-	IDebugClient3.GetOtherOutputMask
-	IDebugClient4.GetOtherOutputMask
-	IDebugClient5.GetOtherOutputMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::GetOtherOutputMask method


## -description


The <b>GetOtherOutputMask</b> method returns the output mask for another client.


## -syntax


````
HRESULT GetOtherOutputMask(
  [in]  PDEBUG_CLIENT Client,
  [out] PULONG        Mask
);
````


## -parameters




### -param Client [in]

Specifies the client whose output mask is desired.


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

<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548080">GetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556750">SetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugClient::GetOtherOutputMask method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

