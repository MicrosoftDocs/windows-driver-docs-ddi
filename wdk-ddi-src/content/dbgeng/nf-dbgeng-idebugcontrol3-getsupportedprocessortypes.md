---
UID: NF:dbgeng.IDebugControl3.GetSupportedProcessorTypes
title: IDebugControl3::GetSupportedProcessorTypes method
author: windows-driver-content
description: The GetSupportedProcessorTypes method returns the processor types supported by the debugger engine.
old-location: debugger\getsupportedprocessortypes.htm
old-project: debugger
ms.assetid: b1a69c60-67e8-46b0-8f2e-7da2c4860ea6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: debugger.getsupportedprocessortypes, dbgeng/IDebugControl2::GetSupportedProcessorTypes, IDebugControl2 interface [Windows Debugging], GetSupportedProcessorTypes method, IDebugControl3::GetSupportedProcessorTypes, GetSupportedProcessorTypes method [Windows Debugging], IDebugControl::GetSupportedProcessorTypes, IDebugControl interface [Windows Debugging], GetSupportedProcessorTypes method, GetSupportedProcessorTypes method [Windows Debugging], IDebugControl interface, dbgeng/IDebugControl::GetSupportedProcessorTypes, IDebugControl3, dbgeng/IDebugControl3::GetSupportedProcessorTypes, IDebugControl_555eef6a-df68-4f94-9cfa-dc31aee27014.xml, IDebugControl, IDebugControl2, GetSupportedProcessorTypes method [Windows Debugging], IDebugControl2 interface, GetSupportedProcessorTypes method [Windows Debugging], IDebugControl3 interface, GetSupportedProcessorTypes, IDebugControl2::GetSupportedProcessorTypes, IDebugControl3 interface [Windows Debugging], GetSupportedProcessorTypes method
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
-	IDebugControl.GetSupportedProcessorTypes
-	IDebugControl2.GetSupportedProcessorTypes
-	IDebugControl3.GetSupportedProcessorTypes
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetSupportedProcessorTypes method


## -description


The <b>GetSupportedProcessorTypes</b> method returns the processor types supported by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.    


## -syntax


````
HRESULT GetSupportedProcessorTypes(
  [in]  ULONG  Start,
  [in]  ULONG  Count,
  [out] PULONG Types
);
````


## -parameters




### -param Start [in]

Specifies the index of the first processor type to return.  The supported processor types are indexed by the numbers zero through the number of supported processor types minus one.  The number of supported processor types can be found using <a href="https://msdn.microsoft.com/library/windows/hardware/ff547966">GetNumberSupportedProcessorTypes</a>.


### -param Count [in]

Specifies the number of processor types to return.


### -param Types [out]

Receives the list of processor types.  The number of elements this array holds is <i>Count</i>.  For a description of the processor types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a>.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547966">GetNumberSupportedProcessorTypes</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548169">GetProcessorTypeNames</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetSupportedProcessorTypes method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

