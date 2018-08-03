---
UID: NF:dbgeng.IDebugControl4.GetStoredEventInformation
title: IDebugControl4::GetStoredEventInformation
author: windows-driver-content
description: The GetStoredEventInformation method retrieves information about an event of interest available in the current target.
old-location: debugger\getstoredeventinformation.htm
tech.root: debugger
ms.assetid: 94cc33bf-cd44-4892-a4e1-991eb6339cc3
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: GetStoredEventInformation, GetStoredEventInformation method [Windows Debugging], GetStoredEventInformation method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetStoredEventInformation method, IDebugControl4.GetStoredEventInformation, IDebugControl4::GetStoredEventInformation, IDebugControl_2d615fc9-52f1-4169-9265-430a1ce0f940.xml, dbgeng/IDebugControl4::GetStoredEventInformation, debugger.getstoredeventinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
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
-	IDebugControl4.GetStoredEventInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetStoredEventInformation


## -description


The <b>GetStoredEventInformation</b> method retrieves information about an event of interest available in the current target.


## -parameters




### -param Type [out]

Receives the type of the stored event.  For a list of possible types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a>.


### -param ProcessId [out]

Receives the process ID of the process in which the event occurred.  If this information is not available, DEBUG_ANY_ID will be returned instead.


### -param ThreadId [out]

Receives the thread ID of the thread in which the last event occurred.  If this information is not available, DEBUG_ANY_ID will be returned instead.


### -param Context [out, optional]

Receives the <a href="https://msdn.microsoft.com/f14b6361-9962-4fa3-bb1a-dfde066754b9">thread context</a> of the stored event.  The type of the thread context is the CONTEXT structure for the target's effective processor at the time of the event.  The <i>Context</i> buffer must be large enough to hold this structure.  If <i>Context</i> is <b>NULL</b>, this information is not returned.


### -param ContextSize [in]

Specifies the size, in bytes, of the buffer that <i>Context</i> specifies.


### -param ContextUsed [out, optional]

Receives the size in bytes of the context.  If <i>ContextUsed</i> is <b>NULL</b>, this information is not returned.


### -param ExtraInformation [out, optional]

Receives extra information about the event.  The contents of this extra information depends on the type of the event.  If <i>ExtraInformation</i> is <b>NULL</b>, this information is not returned.


### -param ExtraInformationSize [in]

Specifies the size, in bytes, of the buffer that <i>ExtraInformation</i> specifies.


### -param ExtraInformationUsed [out, optional]

Receives the size in bytes of extra information.  If <i>ExtraInformationUsed</i> is <b>NULL</b>, this information is not returned.


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



Many targets do not have an event of interest.

If the target is a user-mode minidump file, the dump file generator may store an additional event.  Typically, this is the event that provoked the generator to save the dump file.

For more information, see the topic <a href="https://msdn.microsoft.com/library/windows/hardware/ff543075">Event Information</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546982">GetLastEventInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

