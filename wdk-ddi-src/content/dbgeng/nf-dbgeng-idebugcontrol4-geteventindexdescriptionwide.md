---
UID: NF:dbgeng.IDebugControl4.GetEventIndexDescriptionWide
title: IDebugControl4::GetEventIndexDescriptionWide (dbgeng.h)
description: The GetEventIndexDescriptionWide method describes the specified event in a static list of events for the current target.
old-location: debugger\geteventindexdescriptionwide.htm
tech.root: debugger
ms.assetid: 0153ee1d-93b3-497c-9fbf-e285c3730f72
ms.date: 05/03/2018
ms.keywords: GetEventIndexDescriptionWide, GetEventIndexDescriptionWide method [Windows Debugging], GetEventIndexDescriptionWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetEventIndexDescriptionWide method, IDebugControl4.GetEventIndexDescriptionWide, IDebugControl4::GetEventIndexDescriptionWide, dbgeng/IDebugControl4::GetEventIndexDescriptionWide, debugger.geteventindexdescriptionwide
f1_keywords:
 - "dbgeng/IDebugControl4.GetEventIndexDescriptionWide"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugControl4.GetEventIndexDescriptionWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetEventIndexDescriptionWide


## -description


The <b>GetEventIndexDescriptionWide</b> method describes the specified event in a static list of events for the current target.


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



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getcurrenteventindex">GetCurrentEventIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getnumberevents">GetNumberEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>
 

 

