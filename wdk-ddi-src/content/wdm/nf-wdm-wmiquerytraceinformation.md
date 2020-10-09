---
UID: NF:wdm.WmiQueryTraceInformation
title: WmiQueryTraceInformation function (wdm.h)
description: The WmiQueryTraceInformation routine returns information about a WMI event trace.
old-location: kernel\wmiquerytraceinformation.htm
tech.root: kernel
ms.assetid: 8a6a930a-4267-47be-be00-ab9c102560c4
ms.date: 04/30/2018
keywords: ["WmiQueryTraceInformation function"]
ms.keywords: WmiQueryTraceInformation, WmiQueryTraceInformation routine [Kernel-Mode Driver Architecture], k902_c4cd7b60-d605-465f-b018-f82b6d1144de.xml, kernel.wmiquerytraceinformation, wdm/WmiQueryTraceInformation
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - WmiQueryTraceInformation
 - wdm/WmiQueryTraceInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WmiQueryTraceInformation
---

# WmiQueryTraceInformation function


## -description

The <b>WmiQueryTraceInformation</b> routine returns information about a <a href="/windows-hardware/drivers/kernel/wmi-event-tracing">WMI event trace</a>.

## -parameters

### -param TraceInformationClass 

[in]
Specifies a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_trace_information_class">TRACE_INFORMATION_CLASS</a> enumerator that indicates the type of information to return about an event trace.

### -param TraceInformation 

[out]
A pointer to a caller-allocated output buffer where the routine returns the event trace information specified by <i>TraceInformationClass</i>.

### -param TraceInformationLength 

[in]
Specifies the size, in bytes, of the <i>TraceInformation</i> buffer.

### -param RequiredLength 

[out, optional]
A pointer to the value returned by the routine that specifies the required size, in bytes, of the <i>TraceInformation</i> buffer. The caller should set <i>RequiredLength</i> to <b>NULL</b> if it does not use the required length information.

### -param Buffer 

[in, optional]
A pointer to the query-specific input information that a caller supplies. If caller-supplied information is not required, the caller should set <i>Buffer</i> to <b>NULL</b>.

## -returns

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Success

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <i>TraceInformation</i> buffer is not equal to the required size for the specified event trace information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The trace handle specified by the <b>HistoricalContext</b> member of the (PWNODE_HEADER)<i>Buffer</i> is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
The specified type of event trace information is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The name of the event trace, supplied with a query to return a trace handle given its name, is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_MIX</b></dt>
</dl>
</td>
<td width="60%">
The caller did not supply the information required for the specified event trace information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
The <i>TraceInformation</i> buffer is not large enough to hold an array of all the valid event trace handles.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
A global logger was not found.

</td>
</tr>
</table>

## -remarks

For each type of event trace information specified by <i>TraceInformationClass</i>, the following table provides:

<ul>
<li>
Input requirements

</li>
<li>
Information that <b>WmiQueryTraceInformation</b> returns in the <i>TraceInformation</i> buffer

</li>
</ul>
<table>
<tr>
<th>Value of<i> TraceClassInformation </i></th>
<th>Input requirements</th>
<th>Information returned</th>
</tr>
<tr>
<td>
<b>TraceIdClass</b>

</td>
<td>
<i>TraceInformationLength</i> is equal to the value of <b>sizeof</b>(ULONG).

The size, in bytes of the <i>TraceInformation</i> buffer is greater than or equal to the value of <b>sizeof</b>(ULONG).

The <b>HistoricalContext</b> member of (PWNODE_HEADER)<i>Buffer </i>specifies an event trace handle.

</td>
<td>
*(PULONG)<i>TraceInformation</i> is set to the logger ID of the event trace handle.

</td>
</tr>
<tr>
<td>
<b>TraceHandleClass</b>

</td>
<td>
<i>TraceInformationLength</i> is equal to the value of <b>sizeof</b>(TRACEHANDLE).

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(TRACEHANDLE).

*(PULONG)<i>Buffer</i> is set to a logger ID. 

</td>
<td>
*(PTRACEHANDLE)<i>TraceInformation</i> is set to an event trace handle for the specified logger. If the specified logger ID is zero, an event trace handle for the kernel logger is returned.

</td>
</tr>
<tr>
<td>
<b>TraceEnableFlagsClass</b>

</td>
<td>
<i>TraceInformationLength</i> is greater than or equal to the value of <b>sizeof</b>(ULONG). 

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(ULONG).

The <b>HistoricalContext</b> member of (PWNODE_HEADER)<i>Buffer </i>specifies an event trace handle.

</td>
<td>
*(PULONG)<i>TraceInformation</i> is set to the enable flags that are set for the specified event trace handle.

</td>
</tr>
<tr>
<td>
<b>TraceEnableLevelClass</b>

</td>
<td>
<i>TraceInformationLength</i> is set greater than or equal to the value of <b>sizeof</b>(ULONG). 

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(ULONG).

The <b>HistoricalContext</b> member of (PWNODE_HEADER)<i>Buffer </i>specifies an event trace handle.

</td>
<td>
*(PULONG)<i>TraceInformation</i> is set to the level for the specified event trace handle.

</td>
</tr>
<tr>
<td>
<b>GlobalLoggerHandleClass</b>

</td>
<td>
<i>TraceInformationLength</i> is equal to the value of <b>sizeof</b>(TRACEHANDLE).

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(TRACEHANDLE).

</td>
<td>
*(PTRACEHANDLE)<i>TraceInformation</i> is set to an event trace handle for the global logger.

</td>
</tr>
<tr>
<td>
<b>EventLoggerHandleClass</b>

</td>
<td>
For internal use only.

</td>
<td>
For internal use only.

</td>
</tr>
<tr>
<td>
<b>AllLoggerHandlesClass</b>

</td>
<td>
<i>TraceInformationLength</i> is set to the size, bytes, of an array of <i>m</i> TRACEHANDLE values.

The size, in bytes of the <i>TraceInformation</i> buffer must be greater than or equal to the value of (<i>m</i>*<b>sizeof</b>(TRACEHANDLE)).

</td>
<td>
The <i>TraceInformation</i> buffer contains an array of <i>n</i> trace handles, where <i>n</i> is the minimum of <i>m</i>, the number of caller-supplied event trace handles, and the number of valid event trace handles. The routine returns a status of STATUS_MORE_ENTRIES if the <i>TraceInformation</i> buffer is too small to hold all trace handles.

</td>
</tr>
<tr>
<td>
<b>TraceHandleByNameClass</b>

</td>
<td>
<i>TraceInformationLength</i> is set to the value of <b>sizeof</b>(TRACEHANDLE).

The size, in bytes, of the <i>TraceInformation</i> buffer must be greater than or equal to the value of <b>sizeof</b>(TRACEHANDLE).

(PUNICODE_STRING)<i>Buffer</i> specifies a friendly trace name in Unicode format.

</td>
<td>
*(PTRACEHANDLE)<i>TraceInformation</i> is set to the event trace handle associated with the specified friendly name.

</td>
</tr>
</table>
 

If the caller supplies a non-<b>NULL</b> <i>RequiredLength</i> pointer, <b>WmiQueryTraceInformation</b> also returns the required length for the specified event trace information.

<b>WmiQueryTraceInformation</b> runs at the IRQL of the caller.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiwriteevent">IoWmiWriteEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_trace_information_class">TRACE_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wmilib/nf-wmilib-wmifireevent">WmiFireEvent</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-wmitracemessage">WmiTraceMessage</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-wmitracemessageva">WmiTraceMessageVa</a>