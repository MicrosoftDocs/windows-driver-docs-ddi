---
UID: NS:ksmedia.KSPROPERTY_EXTXPORT_NODE_S
title: KSPROPERTY_EXTXPORT_NODE_S
author: windows-driver-content
description: The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.
old-location: stream\ksproperty_extxport_node_s.htm
old-project: stream
ms.assetid: e0321fa8-610b-4920-8be8-dd91a3452beb
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_EXTXPORT_NODE_S
req.alt-loc: ksmedia.h
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
req.typenames: KSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S
---

# KSPROPERTY_EXTXPORT_NODE_S structure



## -description
The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.



## -syntax

````
typedef struct {
  KSP_NODE NodeProperty;
  union {
    ULONG           Capabilities;
    ULONG           SignalMode;
    ULONG           LoadMedium;
    MEDIUM_INFO     MediumInfo;
    TRANSPORT_STATE XPrtState;
    struct {
      BYTE frame;
      BYTE second;
      BYTE minute;
      BYTE hour;
    } Timecode;
    DWORD           dwTimecode;
    DWORD           dwAbsTrackNumber;
    struct {
      ULONG PayloadSize;
      BYTE  Payload[512];
    } RawAVC;
  } u;
} KSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S;
````


## -struct-fields

### -field NodeProperty

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.


### -field u


### -field Capabilities

Specifies the capabilities of the external transport. For example ED_TRANSCAP_CAN_EJECT, ED_TRANSCAP_CAN_PLAY_BACKWARDS, or ED_TRANSCAP_CAN_BUMP_PLAY. See Remarks.


### -field SignalMode

Specifies the signal mode of the external transport. For example ED_TRANSBASIC_SIGNAL_525_60_SD, ED_TRANSBASIC_SIGNAL_MPEG2TS or ED_TRANSBASIC_SIGNAL_0625_50_MPEG. See Remarks


### -field LoadMedium

Specifies load medium. For example eject, open tray, close tray.


### -field MediumInfo

Describes the medium info.


### -field XPrtState

Describes the external transports state.


### -field Timecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


### -field frame

Specifies the frame. This member is defined for future use.


### -field second

Specifies the second. This member is defined for future use.


### -field minute

Specifies the minute. This member is defined for future use.


### -field hour

Specifies the hour. This member is defined for future use.

</dd>
</dl>

### -field dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


### -field dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.


### -field RawAVC


### -field PayloadSize

Specifies the payload size.


### -field Payload

Describes the payload

</dd>
</dl>
</dd>
</dl>

## -remarks
Any ED_TRANSCAP_Xxx or ED_TRANSBASIC_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-medium_info.md">MEDIUM_INFO</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-transport_state.md">TRANSPORT_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565168">KSPROPERTY_EXTXPORT_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_EXTXPORT_NODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

