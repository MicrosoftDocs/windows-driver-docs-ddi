---
UID: NS:ksmedia.__unnamed_struct_138
title: KSPROPERTY_EXTXPORT_NODE_S (ksmedia.h)
description: The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.
old-location: stream\ksproperty_extxport_node_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_EXTXPORT_NODE_S structure"]
ms.keywords: "*PKSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S structure [Streaming Media Devices], PKSPROPERTY_EXTXPORT_NODE_S, PKSPROPERTY_EXTXPORT_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_EXTXPORT_NODE_S, ksmedia/PKSPROPERTY_EXTXPORT_NODE_S, stream.ksproperty_extxport_node_s, vidcapstruct_06823ca7-5d41-494c-879e-0835ab0b447f.xml"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
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
targetos: Windows
req.typenames: KSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S
f1_keywords:
 - PKSPROPERTY_EXTXPORT_NODE_S
 - ksmedia/PKSPROPERTY_EXTXPORT_NODE_S
 - KSPROPERTY_EXTXPORT_NODE_S
 - ksmedia/KSPROPERTY_EXTXPORT_NODE_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_EXTXPORT_NODE_S
---

# KSPROPERTY_EXTXPORT_NODE_S structure


## -description

The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.

## -struct-fields

### -field NodeProperty

Specifies an initialized <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.

### -field u

### -field u.Capabilities

Specifies the capabilities of the external transport. For example ED_TRANSCAP_CAN_EJECT, ED_TRANSCAP_CAN_PLAY_BACKWARDS, or ED_TRANSCAP_CAN_BUMP_PLAY. See Remarks.

### -field u.SignalMode

Specifies the signal mode of the external transport. For example ED_TRANSBASIC_SIGNAL_525_60_SD, ED_TRANSBASIC_SIGNAL_MPEG2TS or ED_TRANSBASIC_SIGNAL_0625_50_MPEG. See Remarks

### -field u.LoadMedium

Specifies load medium. For example eject, open tray, close tray.

### -field u.MediumInfo

Describes the medium info.

### -field u.XPrtState

Describes the external transports state.

### -field u.Timecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.

### -field u.Timecode.frame

Specifies the frame. This member is defined for future use.

### -field u.Timecode.second

Specifies the second. This member is defined for future use.

### -field u.Timecode.minute

Specifies the minute. This member is defined for future use.

### -field u.Timecode.hour

Specifies the hour. This member is defined for future use.

### -field u.dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.

### -field u.dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.

### -field u.RawAVC

### -field u.RawAVC.PayloadSize

Specifies the payload size.

### -field u.RawAVC.Payload

Describes the payload

## -remarks

Any ED_TRANSCAP_Xxx or ED_TRANSBASIC_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-extxport-state">KSPROPERTY_EXTXPORT_STATE</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-medium_info">MEDIUM_INFO</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-transport_state">TRANSPORT_STATE</a>
