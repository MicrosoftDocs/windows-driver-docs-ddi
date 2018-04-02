---
UID: NF:dbgeng.IDebugClient5.SetOtherOutputMask
title: IDebugClient5::SetOtherOutputMask method
author: windows-driver-content
description: The SetOtherOutputMask method sets the output mask for another client.
old-location: debugger\setotheroutputmask.htm
old-project: debugger
ms.assetid: 09e698cb-09f0-40e0-90ac-0a03c4e5c17b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient interface [Windows Debugging], SetOtherOutputMask method, IDebugClient2 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient2::SetOtherOutputMask, IDebugClient3 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient3::SetOtherOutputMask, IDebugClient4 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient4::SetOtherOutputMask, IDebugClient5, IDebugClient5 interface [Windows Debugging], SetOtherOutputMask method, IDebugClient5::SetOtherOutputMask, IDebugClient::SetOtherOutputMask, IDebugClient_73639f3d-f638-472e-9f30-e33de9321b29.xml, SetOtherOutputMask method [Windows Debugging], SetOtherOutputMask method [Windows Debugging], IDebugClient interface, SetOtherOutputMask method [Windows Debugging], IDebugClient2 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient3 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient4 interface, SetOtherOutputMask method [Windows Debugging], IDebugClient5 interface, SetOtherOutputMask,IDebugClient5.SetOtherOutputMask, dbgeng/IDebugClient2::SetOtherOutputMask, dbgeng/IDebugClient3::SetOtherOutputMask, dbgeng/IDebugClient4::SetOtherOutputMask, dbgeng/IDebugClient5::SetOtherOutputMask, dbgeng/IDebugClient::SetOtherOutputMask, debugger.setotheroutputmask
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
-	IDebugClient.SetOtherOutputMask
-	IDebugClient2.SetOtherOutputMask
-	IDebugClient3.SetOtherOutputMask
-	IDebugClient4.SetOtherOutputMask
-	IDebugClient5.SetOtherOutputMask
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::SetOtherOutputMask method


## -description


The <b>SetOtherOutputMask</b> method sets the output mask for another client.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548066">GetOtherOutputMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550481">IDebugClient2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550488">IDebugClient3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550494">IDebugClient4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556756">SetOutputMask</a>
 

 

