---
UID: NF:storport.StorPortEtwEvent2
title: StorPortEtwEvent2 function (storport.h)
description: The StorPortEtwEvent2 publishes an Event Tracing for Windows (ETW) event to a storage trace channel. The miniport can log two general purpose ETW parameters. The ETW parameters are expressed as two name-value pairs.
old-location: storage\storportetwevent2.htm
tech.root: storage
ms.assetid: A390D684-C675-4140-8E8E-8330FB3192E4
ms.date: 03/29/2018
ms.keywords: STORPORT_ETW_EVENT_KEYWORD_ENUMERATION, STORPORT_ETW_EVENT_KEYWORD_IO, STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE, STORPORT_ETW_EVENT_KEYWORD_POWER, StorPortEtwEvent2, StorPortEtwEvent2 routine [Storage Devices], StorportEtwEventOpcodeDC_Start, StorportEtwEventOpcodeDC_Stop, StorportEtwEventOpcodeExtension, StorportEtwEventOpcodeInfo, StorportEtwEventOpcodeReceive, StorportEtwEventOpcodeReply, StorportEtwEventOpcodeResume, StorportEtwEventOpcodeStart, StorportEtwEventOpcodeStop, StorportEtwEventOpcodeSuspend, StorportEtwLevelCritical, StorportEtwLevelError, StorportEtwLevelInformational, StorportEtwLevelLogAlways, StorportEtwLevelVerbose, StorportEtwLevelWarning, storage.storportetwevent2, storport/StorPortEtwEvent2
ms.topic: function
f1_keywords:
 - "storport/StorPortEtwEvent2"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.1.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortEtwEvent2
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortEtwEvent2 function


## -description


The <b>StorPortEtwEvent2</b> publishes an Event Tracing for Windows (ETW) event to a storage trace channel. The miniport can log two general purpose ETW parameters. The ETW parameters are  expressed as two name-value pairs.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Address [in, optional]

The storage unit device address. This parameter is NULL for adapter devices.


### -param EventId [in]

A miniport defined identifier for the ETW event.


### -param EventDescription [in]

The description text for the event. This text string must be <= STORPORT_ETW_MAX_DESCRIPTION_LENGTH.


### -param EventKeywords [in]

Keyword flags for event categorization. Set to 0 if no keyword is desired. The keywords are a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORPORT_ETW_EVENT_KEYWORD_IO"></a><a id="storport_etw_event_keyword_io"></a><dl>
<dt><b>STORPORT_ETW_EVENT_KEYWORD_IO</b></dt>
</dl>
</td>
<td width="60%">
The event is related to device IO operations.

</td>
</tr>
<tr>
<td width="40%"><a id="STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE"></a><a id="storport_etw_event_keyword_performance"></a><dl>
<dt><b>STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE</b></dt>
</dl>
</td>
<td width="60%">
The event is performance related.

</td>
</tr>
<tr>
<td width="40%"><a id="STORPORT_ETW_EVENT_KEYWORD_POWER"></a><a id="storport_etw_event_keyword_power"></a><dl>
<dt><b>STORPORT_ETW_EVENT_KEYWORD_POWER</b></dt>
</dl>
</td>
<td width="60%">
The event is related to device power.

</td>
</tr>
<tr>
<td width="40%"><a id="STORPORT_ETW_EVENT_KEYWORD_ENUMERATION"></a><a id="storport_etw_event_keyword_enumeration"></a><dl>
<dt><b>STORPORT_ETW_EVENT_KEYWORD_ENUMERATION</b></dt>
</dl>
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
<td width="40%"><a id="StorportEtwLevelLogAlways"></a><a id="storportetwlevellogalways"></a><a id="STORPORTETWLEVELLOGALWAYS"></a><dl>
<dt><b>StorportEtwLevelLogAlways</b></dt>
</dl>
</td>
<td width="60%">
Log the event unconditionally. The event is logged regardless of any filters set.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwLevelCritical"></a><a id="storportetwlevelcritical"></a><a id="STORPORTETWLEVELCRITICAL"></a><dl>
<dt><b>StorportEtwLevelCritical</b></dt>
</dl>
</td>
<td width="60%">
Critical level event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwLevelError"></a><a id="storportetwlevelerror"></a><a id="STORPORTETWLEVELERROR"></a><dl>
<dt><b>StorportEtwLevelError</b></dt>
</dl>
</td>
<td width="60%">
Error level event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwLevelWarning"></a><a id="storportetwlevelwarning"></a><a id="STORPORTETWLEVELWARNING"></a><dl>
<dt><b>StorportEtwLevelWarning</b></dt>
</dl>
</td>
<td width="60%">
Warning level event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwLevelInformational"></a><a id="storportetwlevelinformational"></a><a id="STORPORTETWLEVELINFORMATIONAL"></a><dl>
<dt><b>StorportEtwLevelInformational</b></dt>
</dl>
</td>
<td width="60%">
Informational event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwLevelVerbose"></a><a id="storportetwlevelverbose"></a><a id="STORPORTETWLEVELVERBOSE"></a><dl>
<dt><b>StorportEtwLevelVerbose</b></dt>
</dl>
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
<td width="40%"><a id="StorportEtwEventOpcodeInfo"></a><a id="storportetweventopcodeinfo"></a><a id="STORPORTETWEVENTOPCODEINFO"></a><dl>
<dt><b>StorportEtwEventOpcodeInfo</b></dt>
</dl>
</td>
<td width="60%">
General informational event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeStart"></a><a id="storportetweventopcodestart"></a><a id="STORPORTETWEVENTOPCODESTART"></a><dl>
<dt><b>StorportEtwEventOpcodeStart</b></dt>
</dl>
</td>
<td width="60%">
Device or unit was starting.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeStop"></a><a id="storportetweventopcodestop"></a><a id="STORPORTETWEVENTOPCODESTOP"></a><dl>
<dt><b>StorportEtwEventOpcodeStop</b></dt>
</dl>
</td>
<td width="60%">
Device or unit was stopping. The event corresponds to the last unpaired start event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeDC_Start"></a><a id="storportetweventopcodedc_start"></a><a id="STORPORTETWEVENTOPCODEDC_START"></a><dl>
<dt><b>StorportEtwEventOpcodeDC_Start</b></dt>
</dl>
</td>
<td width="60%">
A data collection starting event. These are rundown event types.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeDC_Stop"></a><a id="storportetweventopcodedc_stop"></a><a id="STORPORTETWEVENTOPCODEDC_STOP"></a><dl>
<dt><b>StorportEtwEventOpcodeDC_Stop</b></dt>
</dl>
</td>
<td width="60%">
A data collection stopping event. These are rundown event types.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeExtension"></a><a id="storportetweventopcodeextension"></a><a id="STORPORTETWEVENTOPCODEEXTENSION"></a><dl>
<dt><b>StorportEtwEventOpcodeExtension</b></dt>
</dl>
</td>
<td width="60%">
An extension event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeReply"></a><a id="storportetweventopcodereply"></a><a id="STORPORTETWEVENTOPCODEREPLY"></a><dl>
<dt><b>StorportEtwEventOpcodeReply</b></dt>
</dl>
</td>
<td width="60%">
A reply event.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeResume"></a><a id="storportetweventopcoderesume"></a><a id="STORPORTETWEVENTOPCODERESUME"></a><dl>
<dt><b>StorportEtwEventOpcodeResume</b></dt>
</dl>
</td>
<td width="60%">
Device or unit was resuming after suspend.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeSuspend"></a><a id="storportetweventopcodesuspend"></a><a id="STORPORTETWEVENTOPCODESUSPEND"></a><dl>
<dt><b>StorportEtwEventOpcodeSuspend</b></dt>
</dl>
</td>
<td width="60%">
Device or unit is  suspended pending completion of another operation.

</td>
</tr>
<tr>
<td width="40%"><a id="StorportEtwEventOpcodeReceive"></a><a id="storportetweventopcodereceive"></a><a id="STORPORTETWEVENTOPCODERECEIVE"></a><dl>
<dt><b>StorportEtwEventOpcodeReceive</b></dt>
</dl>
</td>
<td width="60%">
 Transfer of activity is received from another component.

</td>
</tr>
</table>
 


### -param Srb [in, optional]

A pointer to the SRB associated with the logged event. If this parameter contains a valid SRB, this SRB pointer and the associated SRB pointer are logged.


### -param Parameter1Name [in, optional]

A description of the of the meaning of <i>Parameter1Value</i>. This parameter name string must be <= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.


### -param Parameter1Value [in]

The value for parameter 1.


### -param Parameter2Name [in, optional]

A description of the of the meaning of <i>Parameter2Value</i>. This parameter name string must be <= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.


### -param Parameter2Value [in]

The value for parameter 2.


## -returns



<b>StorPortEtwEvent2</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The event published successfully storage ETW channel.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
Tracing is not enabled for storage events.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> parameter is NULL.

-or-

<i>EventDescription</i> is NULL.

-or-

<i>EventDescription</i> is greater than the maximum name length.

-or-

An ETW parameter name is greater than the maximum name length.

</td>
</tr>
</table>
 




## -remarks



If any parameter is not named, ParameterXName = NULL, the routine will set the corresponding parameter value to 0.

Events generated from StorPort miniport drivers are published to the "Microsoft-Windows-Storage-Storport/Diagnose" ETW channel.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportetwevent4">StorPortEtwEvent4</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportetwevent8">StorPortEtwEvent8</a>
 

 

