---
UID: NF:dbgeng.IDebugControl2.GetProcessorTypeNames
title: IDebugControl2::GetProcessorTypeNames method
author: windows-driver-content
description: The GetProcessorTypeNames method returns the full name and abbreviated name of the specified processor type.
old-location: debugger\getprocessortypenames.htm
old-project: debugger
ms.assetid: cee254a5-7b77-4cab-b02c-69b1f9e3fe02
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetProcessorTypeNames method [Windows Debugging], GetProcessorTypeNames method [Windows Debugging], IDebugControl interface, GetProcessorTypeNames method [Windows Debugging], IDebugControl2 interface, GetProcessorTypeNames method [Windows Debugging], IDebugControl3 interface, GetProcessorTypeNames,IDebugControl2.GetProcessorTypeNames, IDebugControl interface [Windows Debugging], GetProcessorTypeNames method, IDebugControl2, IDebugControl2 interface [Windows Debugging], GetProcessorTypeNames method, IDebugControl2::GetProcessorTypeNames, IDebugControl3 interface [Windows Debugging], GetProcessorTypeNames method, IDebugControl3::GetProcessorTypeNames, IDebugControl::GetProcessorTypeNames, IDebugControl_f14b5f52-cf94-458b-bd1e-61c3ad66a597.xml, dbgeng/IDebugControl2::GetProcessorTypeNames, dbgeng/IDebugControl3::GetProcessorTypeNames, dbgeng/IDebugControl::GetProcessorTypeNames, debugger.getprocessortypenames
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
-	IDebugControl.GetProcessorTypeNames
-	IDebugControl2.GetProcessorTypeNames
-	IDebugControl3.GetProcessorTypeNames
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl2::GetProcessorTypeNames method


## -description


The <b>GetProcessorTypeNames</b>  method returns the full name and abbreviated name of the specified processor type.


## -parameters




### -param Type [in]

Specifies the type of the processor whose name is requested.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a> for a list of possible values.


### -param FullNameBuffer [out, optional]

Receives the full name of the processor type.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param FullNameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>FullNameBuffer</i> specifies.


### -param FullNameSize [out, optional]

Receives the size in characters of the full name of the processor type.  If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBuffer [out, optional]

Receives the abbreviated name of the processor type.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param AbbrevNameBufferSize [in]

Specifies the size, in characters, of the buffer that <i>AbbrevNameBuffer</i> specifies.


### -param AbbrevNameSize [out, optional]

Receives the size in characters of the abbreviated name of the processor type.  If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, at least one of <i>FullNameBuffer</i> or <i>AbbrevNameBuffer</i> was too small for the corresponding name, so the name was truncated.

</td>
</tr>
</table>
 




## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548438">GetSupportedProcessorTypes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550508">IDebugControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550512">IDebugControl2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550519">IDebugControl3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetProcessorTypeNames method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
