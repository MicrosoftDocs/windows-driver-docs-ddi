---
UID: NF:dbgeng.IDebugControl4.GetEventIndexDescriptionWide
title: IDebugControl4::GetEventIndexDescriptionWide method
author: windows-driver-content
description: The GetEventIndexDescriptionWide method describes the specified event in a static list of events for the current target.
old-location: debugger\geteventindexdescriptionwide.htm
old-project: debugger
ms.assetid: 0153ee1d-93b3-497c-9fbf-e285c3730f72
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDebugControl4 interface [Windows Debugging], GetEventIndexDescriptionWide method, IDebugControl4::GetEventIndexDescriptionWide, GetEventIndexDescriptionWide method [Windows Debugging], GetEventIndexDescriptionWide method [Windows Debugging], IDebugControl4 interface, dbgeng/IDebugControl4::GetEventIndexDescriptionWide, GetEventIndexDescriptionWide, debugger.geteventindexdescriptionwide, IDebugControl4
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
-	IDebugControl4.GetEventIndexDescriptionWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetEventIndexDescriptionWide method


## -description


The <b>GetEventIndexDescriptionWide</b> method describes the specified event in a static list of events for the current target.


## -syntax


````
HRESULT GetEventIndexDescriptionWide(
  [in]            ULONG  Index,
  [in]            ULONG  Which,
  [in, optional]  PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG DescSize
);
````


## -parameters




### -param Index [in]

Specifies the index of the event whose description will be returned.


### -param Which [in]

Specifies which piece of the event description to return.  Currently only DEBUG_EINDEX_NAME is supported; this returns the name of the event.


### -param Buffer [in, optional]

Receives the description of the event.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer </i>buffer.


### -param DescSize [out, optional]

Receives the size, in characters, of the description.  If <i>DescSize</i> is <b>NULL</b>, this information is not returned.


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



The amount of descriptive information available for a particular target varies depending on the type of the target.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545755">GetCurrentEventIndex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetEventIndexDescriptionWide method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

