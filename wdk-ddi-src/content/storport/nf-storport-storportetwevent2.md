---
UID: NF:storport.StorPortEtwEvent2
title: StorPortEtwEvent2 function
author: windows-driver-content
description: The StorPortEtwEvent2 publishes an Event Tracing for Windows (ETW) event to a storage trace channel. The miniport can log two general purpose ETW parameters. The ETW parameters are expressed as two name-value pairs.
old-location: storage\storportetwevent2.htm
old-project: storage
ms.assetid: A390D684-C675-4140-8E8E-8330FB3192E4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortEtwEvent2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortEtwEvent2
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortEtwEvent2 function



## -description
The <b>StorPortEtwEvent2</b> publishes an Event Tracing for Windows (ETW) event to a storage trace channel. The miniport can log two general purpose ETW parameters. The ETW parameters are  expressed as two name-value pairs.



## -syntax

````
ULONG StorPortEtwEvent2(
  _In_     PVOID                     HwDeviceExtension,
  _In_opt_ PSTOR_ADDRESS             Address,
  _In_     ULONG                     EventId,
  _In_     PWSTR                     EventDescription,
  _In_     ULONGLONG                 EventKeywords,
  _In_     STORPORT_ETW_LEVEL        EventLevel,
  _In_     STORPORT_ETW_EVENT_OPCODE EventOpcode,
  _In_opt_ PSCSI_REQUEST_BLOCK       Srb,
  _In_opt_ PWSTR                     Parameter1Name,
  _In_     ULONGLONG                 Parameter1Value,
  _In_opt_ PWSTR                     Parameter2Name,
  _In_     ULONGLONG                 Parameter2Value
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, optional]

The storage unit device address. This parameter is NULL for adapter devices.


### -param EventId [in]

A miniport defined identifier for the ETW event.


### -param EventDescription [in]

The description text for the event. This text string must be &lt;= STORPORT_ETW_MAX_DESCRIPTION_LENGTH.


### -param EventKeywords [in]

Keyword flags for event categorization. Set to 0 if no keyword is desired. The keywords are a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param STORPORT_ETW_EVENT_KEYWORD_IO

</td>
<td width="60%">
The event is related to device IO operations.

</td>
</tr>
<tr>

### -param STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE

</td>
<td width="60%">
The event is performance related.

</td>
</tr>
<tr>

### -param STORPORT_ETW_EVENT_KEYWORD_POWER

</td>
<td width="60%">
The event is related to device power.

</td>
</tr>
<tr>

### -param STORPORT_ETW_EVENT_KEYWORD_ENUMERATION

</td>
<td width="60%">
The event is related to device enumeration.

</td>
</tr>
</table>
 


### -param EventLevel [in]

The event level. This value can indicate the importance or severity of the event. This is one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param StorportEtwLevelLogAlways

</td>
<td width="60%">
Log the event unconditionally. The event is logged regardless of any filters set.

</td>
</tr>
<tr>

### -param StorportEtwLevelCritical

</td>
<td width="60%">
Critical level event.

</td>
</tr>
<tr>

### -param StorportEtwLevelError

</td>
<td width="60%">
Error level event.

</td>
</tr>
<tr>

### -param StorportEtwLevelWarning

</td>
<td width="60%">
Warning level event.

</td>
</tr>
<tr>

### -param StorportEtwLevelInformational

</td>
<td width="60%">
Informational event.

</td>
</tr>
<tr>

### -param StorportEtwLevelVerbose

</td>
<td width="60%">
Verbose event information provided.

</td>
</tr>
</table>
 


### -param EventOpcode [in]

The operational nature of the event. This is one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param StorportEtwEventOpcodeInfo

</td>
<td width="60%">
General informational event.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeStart

</td>
<td width="60%">
Device or unit was starting.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeStop

</td>
<td width="60%">
Device or unit was stopping. The event corresponds to the last unpaired start event.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeDC_Start

</td>
<td width="60%">
A data collection starting event. These are rundown event types.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeDC_Stop

</td>
<td width="60%">
A data collection stopping event. These are rundown event types.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeExtension

</td>
<td width="60%">
An extension event.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeReply

</td>
<td width="60%">
A reply event.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeResume

</td>
<td width="60%">
Device or unit was resuming after suspend.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeSuspend

</td>
<td width="60%">
Device or unit is  suspended pending completion of another operation.

</td>
</tr>
<tr>

### -param StorportEtwEventOpcodeReceive

</td>
<td width="60%">
 Transfer of activity is received from another component.

</td>
</tr>
</table>
 


### -param Srb [in, optional]

A pointer to the SRB associated with the logged event. If this parameter contains a valid SRB, this SRB pointer and the associated SRB pointer are logged.


### -param Parameter1Name [in, optional]

A description of the of the meaning of <i>Parameter1Value</i>. This parameter name string must be &lt;= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.


### -param Parameter1Value [in]

The value for parameter 1.


### -param Parameter2Name [in, optional]

A description of the of the meaning of <i>Parameter2Value</i>. This parameter name string must be &lt;= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.


### -param Parameter2Value [in]

The value for parameter 2.


## -returns
<b>StorPortEtwEvent2</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The event published successfully storage ETW channel.
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>Tracing is not enabled for storage events.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>HwDeviceExtension</i> parameter is NULL.

-or-

<i>EventDescription</i> is NULL.

-or-

<i>EventDescription</i> is greater than the maximum name length.

-or-

An ETW parameter name is greater than the maximum name length.

 


## -remarks
If any parameter is not named, ParameterXName = NULL, the routine will set the corresponding parameter value to 0.

Events generated from StorPort miniport drivers are published to the "Microsoft-Windows-Storage-Storport/Diagnose" ETW channel.


## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportetwevent4.md">StorPortEtwEvent4</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportetwevent8.md">StorPortEtwEvent8</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortEtwEvent2 routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

