---
UID: NE:storport._STORPORT_ETW_LEVEL
tech.root: storage
title: STORPORT_ETW_LEVEL
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the STORPORT_ETW_LEVEL enumeration.
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
 - _STORPORT_ETW_LEVEL
 - PSTORPORT_ETW_LEVEL
 - STORPORT_ETW_LEVEL
f1_keywords:
 - _STORPORT_ETW_LEVEL
 - storport/_STORPORT_ETW_LEVEL
 - PSTORPORT_ETW_LEVEL
 - storport/PSTORPORT_ETW_LEVEL
 - STORPORT_ETW_LEVEL
 - storport/STORPORT_ETW_LEVEL
dev_langs:
 - c++
helpviewer_keywords:
 - _STORPORT_ETW_LEVEL
---

## -description

The **STORPORT_ETW_LEVEL** enumeration defines the level of importance or severity of an ETW event.

## -enum-fields

### -field StorportEtwLevelLogAlways:0

Log the event unconditionally. An event with this level is logged without any throttling.

### -field StorportEtwLevelCritical:1

Indicates a critical condition that could cause severe problems such as a system crash. An event with this level is logged without any throttling.

### -field StorportEtwLevelError:2

Indicates an error condition. Events at this level are throttled at the specific device instance at which the miniport event is targeted. There's an upper limit on the count of events per hour at the device instance.

### -field StorportEtwLevelWarning:3

Indicates a potential issue or something unexpected. Like error-level events, warning-level events are throttled at the specific device instance level.

### -field StorportEtwLevelInformational:4

Indicates an informational event, such as status. Informational events are also throttled at the specific device instance level.

### -field StorportEtwLevelVerbose:5

Indicates that the event provides detailed tracing information, typically for debugging purposes. Verbose-level events aren't throttled.

### -field StorportEtwLevelMax

Maximum value for the enumeration.

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
