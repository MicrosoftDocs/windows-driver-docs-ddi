---
UID: NF:dbgeng.IDebugControl4.GetStoredEventInformation
title: IDebugControl4::GetStoredEventInformation method
author: windows-driver-content
description: The GetStoredEventInformation method retrieves information about an event of interest available in the current target.
old-location: debugger\getstoredeventinformation.htm
old-project: debugger
ms.assetid: 94cc33bf-cd44-4892-a4e1-991eb6339cc3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::GetStoredEventInformation, GetStoredEventInformation
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
req.alt-api: IDebugControl4.GetStoredEventInformation
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

# IDebugControl4::GetStoredEventInformation method



## -description
The <b>GetStoredEventInformation</b> method retrieves information about an event of interest available in the current target.



## -syntax

````
HRESULT GetStoredEventInformation(
  [out]           PULONG Type,
  [out]           PULONG ProcessId,
  [out]           PULONG ThreadId,
  [out, optional] PVOID  Context,
  [in]            ULONG  ContextSize,
  [out, optional] PULONG ContextUsed,
  [out, optional] PVOID  ExtraInformation,
  [in]            ULONG  ExtraInformationSize,
  [out, optional] PULONG ExtraInformationUsed
);
````


## -parameters

### -param Type [out]

Receives the type of the stored event.  For a list of possible types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541478">DEBUG_EVENT_XXX</a>.


### -param ProcessId [out]

Receives the process ID of the process in which the event occurred.  If this information is not available, DEBUG_ANY_ID will be returned instead.


### -param ThreadId [out]

Receives the thread ID of the thread in which the last event occurred.  If this information is not available, DEBUG_ANY_ID will be returned instead.


### -param Context [out, optional]

Receives the <a href="debugger.scopes_and_symbol_groups#thread_context#thread_context">thread context</a> of the stored event.  The type of the thread context is the CONTEXT structure for the target's effective processor at the time of the event.  The <i>Context</i> buffer must be large enough to hold this structure.  If <i>Context</i> is <b>NULL</b>, this information is not returned.


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Many targets do not have an event of interest.

If the target is a user-mode minidump file, the dump file generator may store an additional event.  Typically, this is the event that provoked the generator to save the dump file.

For more information, see the topic <a href="https://msdn.microsoft.com/library/windows/hardware/ff543075">Event Information</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546982">GetLastEventInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetStoredEventInformation method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

