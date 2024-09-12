---
UID: NE:storport._STORPORT_ETW_EVENT_OPCODE
tech.root: storage
title: STORPORT_ETW_EVENT_OPCODE
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the STORPORT_ETW_EVENT_OPCODE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_ETW_EVENT_OPCODE
 - PSTORPORT_ETW_EVENT_OPCODE
 - STORPORT_ETW_EVENT_OPCODE
f1_keywords:
 - _STORPORT_ETW_EVENT_OPCODE
 - storport/_STORPORT_ETW_EVENT_OPCODE
 - PSTORPORT_ETW_EVENT_OPCODE
 - storport/PSTORPORT_ETW_EVENT_OPCODE
 - STORPORT_ETW_EVENT_OPCODE
 - storport/STORPORT_ETW_EVENT_OPCODE
dev_langs:
 - c++
helpviewer_keywords:
 - _STORPORT_ETW_EVENT_OPCODE
---

## -description

A **STORPORT_ETW_EVENT_OPCODE** enumeration defines operational nature of an ETW event.

## -enum-fields

### -field StorportEtwEventOpcodeInfo:0

Indicates a general, informational event.

### -field StorportEtwEventOpcodeStart:1

The device or unit was started.

### -field StorportEtwEventOpcodeStop:2

The device or unit was stopped. The event corresponses to the last unpaired start event.

### -field StorportEtwEventOpcodeDC_Start:3

Indicates a data collection starting event. These are rundown event types.

### -field StorportEtwEventOpcodeDC_Stop:4

Indicates a data collection stopping event. These are rundown event types.

### -field StorportEtwEventOpcodeExtension:5

Indicates an extension event.

### -field StorportEtwEventOpcodeReply:6

Indicates a reply event.

### -field StorportEtwEventOpcodeResume:7

The device or unit was resumed after a suspend event.

### -field StorportEtwEventOpcodeSuspend:8

The device or unit is suspended pending completion of another operation.

### -field StorportEtwEventOpcodeSend:9

Indicates that transfer of activity is sent to another component.

### -field StorportEtwEventOpcodeReceive:240

Indicates that transfer of activity is received from another component.

## -remarks

## -see-also

[**StorPortEtwChannelEvent2**](nf-storport-storportetwchannelevent2.md)

[**StorPortEtwChannelEvent4**](nf-storport-storportetwchannelevent4.md)

[**StorPortEtwChannelEvent8**](nf-storport-storportetwchannelevent8.md)

[**StorPortEtwEvent2**](nf-storport-storportetwevent2.md)

[**StorPortEtwEvent4**](nf-storport-storportetwevent4.md)

[**StorPortEtwEvent8**](nf-storport-storportetwevent8.md)

[**StorPortEtwLogByteStream**](nf-storport-storportetwlogbytestream.md)

[**StorPortNvmeMiniportEvent**](nf-storport-storportnvmeminiportevent.md)
