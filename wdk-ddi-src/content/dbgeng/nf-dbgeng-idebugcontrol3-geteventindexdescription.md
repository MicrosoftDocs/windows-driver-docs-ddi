---
UID: NF:dbgeng.IDebugControl3.GetEventIndexDescription
title: IDebugControl3::GetEventIndexDescription method
author: windows-driver-content
description: The GetEventIndexDescription method describes the specified event in a static list of events for the current target.
old-location: debugger\geteventindexdescription.htm
old-project: debugger
ms.assetid: 75aace9d-3f1e-4002-82e6-d581903da4f9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetEventIndexDescription, GetEventIndexDescription
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
req.alt-api: IDebugControl3.GetEventIndexDescription
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

# IDebugControl3::GetEventIndexDescription method



## -description
The <b>GetEventIndexDescription</b>  method describes the specified event in a static list of events for the current target.



## -syntax

````
HRESULT GetEventIndexDescription(
  [in]            ULONG  Index,
  [in]            ULONG  Which,
  [in, optional]  PSTR   Buffer,
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
The amount of descriptive information available for a particular target varies depending on the type of the target.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547906">GetNumberEvents</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545755">GetCurrentEventIndex</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl3::GetEventIndexDescription method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

