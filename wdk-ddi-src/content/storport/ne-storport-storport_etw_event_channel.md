---
UID: NE:storport._STORPORT_ETW_EVENT_CHANNEL
tech.root: storage
title: STORPORT_ETW_EVENT_CHANNEL
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STORPORT_ETW_EVENT_CHANNEL identifies the event channels of Storport to which miniport can log an event.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10 version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_ETW_EVENT_CHANNEL
 - PSTORPORT_ETW_EVENT_CHANNEL
 - STORPORT_ETW_EVENT_CHANNEL
f1_keywords:
 - _STORPORT_ETW_EVENT_CHANNEL
 - storport/_STORPORT_ETW_EVENT_CHANNEL
 - PSTORPORT_ETW_EVENT_CHANNEL
 - storport/PSTORPORT_ETW_EVENT_CHANNEL
 - STORPORT_ETW_EVENT_CHANNEL
 - storport/STORPORT_ETW_EVENT_CHANNEL
dev_langs:
 - c++
---

## -description

The **STORPORT_ETW_EVENT_CHANNEL** enumeration identifies the event channels of Storport to which miniport can log an event.

## -enum-fields

### -field StorportEtwEventDiagnostic

Storport's diagnostic channel (*Microsoft-Windows-Storage-Storport/Diagnose*).

### -field StorportEtwEventOperational

Storport's operational channel (*Microsoft-Windows-Storage-Storport/Operational*).

### -field StorportEtwEventHealth

Storport's health channel (*Microsoft-Windows-Storage-Storport/Health*).

## -remarks

**STORPORT_ETW_EVENT_CHANNEL** is identified in the **Channel** member of a [**STOR_SET_EVENT_LOGGING**](ns-storport-stor_set_event_logging.md) structure.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**STOR_SET_EVENT_LOGGING**](ns-storport-stor_set_event_logging.md)
