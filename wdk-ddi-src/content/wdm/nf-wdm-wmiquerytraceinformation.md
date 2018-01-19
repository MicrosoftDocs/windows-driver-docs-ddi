---
UID: NF:wdm.WmiQueryTraceInformation
title: WmiQueryTraceInformation function
author: windows-driver-content
description: The WmiQueryTraceInformation routine returns information about a WMI event trace.
old-location: kernel\wmiquerytraceinformation.htm
old-project: kernel
ms.assetid: 8a6a930a-4267-47be-be00-ab9c102560c4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WmiQueryTraceInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WmiQueryTraceInformation
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WmiQueryTraceInformation function



## -description
The <b>WmiQueryTraceInformation</b> routine returns information about a <a href="https://msdn.microsoft.com/72505a9a-830a-4529-ba73-31af0fedfeec">WMI event trace</a>.



## -syntax

````
NTSTATUS WmiQueryTraceInformation(
  _In_      TRACE_INFORMATION_CLASS TraceInformationClass,
  _Out_     PVOID                   TraceInformation,
  _In_      ULONG                   TraceInformationLength,
  _Out_opt_ PULONG                  RequiredLength,
  _In_opt_  PVOID                   Buffer
);
````


## -parameters

### -param TraceInformationClass [in]

Specifies a <a href="..\wdm\ne-wdm-_trace_information_class.md">TRACE_INFORMATION_CLASS</a> enumerator that indicates the type of information to return about an event trace.


### -param TraceInformation [out]

A pointer to a caller-allocated output buffer where the routine returns the event trace information specified by <i>TraceInformationClass</i>.


### -param TraceInformationLength [in]

Specifies the size, in bytes, of the <i>TraceInformation</i> buffer.


### -param RequiredLength [out, optional]

A pointer to the value returned by the routine that specifies the required size, in bytes, of the <i>TraceInformation</i> buffer. The caller should set <i>RequiredLength</i> to <b>NULL</b> if it does not use the required length information.


### -param Buffer [in, optional]

A pointer to the query-specific input information that a caller supplies. If caller-supplied information is not required, the caller should set <i>Buffer</i> to <b>NULL</b>. 


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Success
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <i>TraceInformation</i> buffer is not equal to the required size for the specified event trace information.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The trace handle specified by the <b>HistoricalContext</b> member of the (PWNODE_HEADER)<i>Buffer</i> is not valid.
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>The specified type of event trace information is not valid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The name of the event trace, supplied with a query to return a trace handle given its name, is not valid.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl>The caller did not supply the information required for the specified event trace information.
<dl>
<dt><b>STATUS_MORE_ENTRIES</b></dt>
</dl>The <i>TraceInformation</i> buffer is not large enough to hold an array of all the valid event trace handles.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>A global logger was not found.

 


## -remarks
For each type of event trace information specified by <i>TraceInformationClass</i>, the following table provides:

Input requirements

Information that <b>WmiQueryTraceInformation</b> returns in the <i>TraceInformation</i> buffer

<b>TraceIdClass</b>

<i>TraceInformationLength</i> is equal to the value of <b>sizeof</b>(ULONG).

The size, in bytes of the <i>TraceInformation</i> buffer is greater than or equal to the value of <b>sizeof</b>(ULONG).

The <b>HistoricalContext</b> member of (PWNODE_HEADER)<i>Buffer </i>specifies an event trace handle.

*(PULONG)<i>TraceInformation</i> is set to the logger ID of the event trace handle.

<b>TraceHandleClass</b>

<i>TraceInformationLength</i> is equal to the value of <b>sizeof</b>(TRACEHANDLE).

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(TRACEHANDLE).

*(PULONG)<i>Buffer</i> is set to a logger ID. 

*(PTRACEHANDLE)<i>TraceInformation</i> is set to an event trace handle for the specified logger. If the specified logger ID is zero, an event trace handle for the kernel logger is returned.

<b>TraceEnableFlagsClass</b>

<i>TraceInformationLength</i> is greater than or equal to the value of <b>sizeof</b>(ULONG). 

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(ULONG).

*(PULONG)<i>TraceInformation</i> is set to the enable flags that are set for the specified event trace handle.

<b>TraceEnableLevelClass</b>

<i>TraceInformationLength</i> is set greater than or equal to the value of <b>sizeof</b>(ULONG). 

*(PULONG)<i>TraceInformation</i> is set to the level for the specified event trace handle.

<b>GlobalLoggerHandleClass</b>

*(PTRACEHANDLE)<i>TraceInformation</i> is set to an event trace handle for the global logger.

<b>EventLoggerHandleClass</b>

For internal use only.

<b>AllLoggerHandlesClass</b>

<i>TraceInformationLength</i> is set to the size, bytes, of an array of <i>m</i> TRACEHANDLE values.

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of (<i>m</i>*<b>sizeof</b>(TRACEHANDLE)).

The <i>TraceInformation</i> buffer contains an array of <i>n</i> trace handles, where <i>n</i> is the minimum of <i>m</i>, the number of caller-supplied event trace handles, and the number of valid event trace handles. The routine returns a status of STATUS_MORE_ENTRIES if the <i>TraceInformation</i> buffer is too small to hold all trace handles.

<b>TraceHandleByNameClass</b>

<i>TraceInformationLength</i> is set to the value of <b>sizeof</b>(TRACEHANDLE).

The size, in bytes, of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(TRACEHANDLE).

(PUNICODE_STRING)<i>Buffer</i> specifies a friendly trace name in Unicode format.

*(PTRACEHANDLE)<i>TraceInformation</i> is set to the event trace handle associated with the specified friendly name.

If the caller supplies a non-<b>NULL</b> <i>RequiredLength</i> pointer, <b>WmiQueryTraceInformation</b> also returns the required length for the specified event trace information.

<b>WmiQueryTraceInformation</b> runs at the IRQL of the caller.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iowmiwriteevent.md">IoWmiWriteEvent</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_trace_information_class.md">TRACE_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\wmilib\nf-wmilib-wmifireevent.md">WmiFireEvent</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-wmitracemessage.md">WmiTraceMessage</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-wmitracemessageva.md">WmiTraceMessageVa</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WmiQueryTraceInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

