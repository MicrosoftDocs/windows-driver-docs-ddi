---
UID: NF:dbgeng.IDebugClient4.SetOtherOutputMask
title: IDebugClient4::SetOtherOutputMask method
author: windows-driver-content
description: The SetOtherOutputMask method sets the output mask for another client.
old-location: debugger\setotheroutputmask.htm
old-project: debugger
ms.assetid: 09e698cb-09f0-40e0-90ac-0a03c4e5c17b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 4, :, C, D, I, IDebugClient, IDebugClient interface [Windows Debugging], SetOtherOutputMask method, IDebugClient2, IDebugClient2 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient2::SetOtherOutputMask, IDebugClient3, IDebugClient3 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient3::SetOtherOutputMask, IDebugClient4, IDebugClient4 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient4::SetOtherOutputMask, IDebugClient5 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient5::SetOtherOutputMask, IDebugClient::SetOtherOutputMask, IDebugClient_73639f3d-f638-472e-9f30-e33de9321b29.xml, M, O, S, SetOtherOutputMask method [Windows Debugging], SetOtherOutputMask method [Windows Debugging], IDebugClient interface, SetOtherOutputMask method [Windows Debugging], IDebugClient2 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient3 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient4 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient5 interface, SetOtherOutputMask,IDebugClient.SetOtherOutputMask, SetOtherOutputMask,IDebugClient2.SetOtherOutputMask, SetOtherOutputMask,IDebugClient3.SetOtherOutputMask, SetOtherOutputMask,IDebugClient4.SetOtherOutputMask, a, b, dbgeng/IDebugClient2::SetOtherOutputMask, dbgeng/IDebugClient3::SetOtherOutputMask, dbgeng/IDebugClient4::SetOtherOutputMask, dbgeng/IDebugClient5::SetOtherOutputMask, dbgeng/IDebugClient::SetOtherOutputMask, debugger.setotheroutputmask, e, g, h, i, k, l, n, p, r, s, t, u"
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
-	IDebugClient.SetOtherOutputMask
-	IDebugClient2.SetOtherOutputMask
-	IDebugClient3.SetOtherOutputMask
-	IDebugClient4.SetOtherOutputMask
-	IDebugClient5.SetOtherOutputMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient4::SetOtherOutputMask method


## -description


The <b>SetOtherOutputMask</b> method sets the output mask for another client.


## -syntax


````
HRESULT SetOtherOutputMask(
  [in] PDEBUG_CLIENT Client,
  [in] ULONG         Mask
);
````


## -parameters




### -param Client [in]

Specifies the client whose output mask will be set.


### -param Mask [in]

Specifies the new output mask for the client.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541518">DEBUG_OUTPUT_XXX</a> for a description of the possible values for <i>Mask</i>.


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

<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::SetOtherOutputMask method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

