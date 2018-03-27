---
UID: NF:dbgeng.IDebugControl3.GetActualProcessorType
title: IDebugControl3::GetActualProcessorType method
author: windows-driver-content
description: The GetActualProcessorType method returns the processor type of the physical processor of the computer that is running the target.
old-location: debugger\getactualprocessortype.htm
old-project: debugger
ms.assetid: c02be0a4-f82a-4895-bbae-21f6ffdc5466
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetActualProcessorType method [Windows Debugging], GetActualProcessorType method [Windows Debugging], IDebugControl interface, GetActualProcessorType method [Windows Debugging], IDebugControl2 interface, GetActualProcessorType method [Windows Debugging], IDebugControl3 interface, GetActualProcessorType,IDebugControl3.GetActualProcessorType, IDebugControl interface [Windows Debugging], GetActualProcessorType method, IDebugControl2 interface [Windows Debugging], GetActualProcessorType method, IDebugControl2::GetActualProcessorType, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetActualProcessorType method, IDebugControl3::GetActualProcessorType, IDebugControl::GetActualProcessorType, IDebugControl_5511971f-2155-4ba3-b0f3-9bcd91b29555.xml, dbgeng/IDebugControl2::GetActualProcessorType, dbgeng/IDebugControl3::GetActualProcessorType, dbgeng/IDebugControl::GetActualProcessorType, debugger.getactualprocessortype
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
-	IDebugControl.GetActualProcessorType
-	IDebugControl2.GetActualProcessorType
-	IDebugControl3.GetActualProcessorType
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetActualProcessorType method


## -description


The <b>GetActualProcessorType</b> method returns the processor type of the physical processor of the computer that is running the target.


## -parameters




### -param Type [out]

Receives the type of the processor.  The processor types are listed in the following table.     

<table>
<tr>
<th>Value</th>
<th>Processor</th>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_I386

</td>
<td>
x86 architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_ARM

</td>
<td>
ARM architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_IA64

</td>
<td>
Intel Itanium architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_AMD64

</td>
<td>
x64 architecture

</td>
</tr>
<tr>
<td>
IMAGE_FILE_MACHINE_EBC

</td>
<td>
EFI byte code architecture

</td>
</tr>
</table>
 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546595">GetEffectiveProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546670">GetExecutingProcessorType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetActualProcessorType method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

