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
ms.keywords: KSPROPERTY_EXTXPORT_NODE_S, stream.ksproperty_extxport_node_s, KSPROPERTY_EXTXPORT_NODE_S structure [Streaming Media Devices], PKSPROPERTY_EXTXPORT_NODE_S, ksmedia/PKSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S, PKSPROPERTY_EXTXPORT_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_EXTXPORT_NODE_S, vidcapstruct_06823ca7-5d41-494c-879e-0835ab0b447f.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_EXTXPORT_NODE_S
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S"
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




#### - u



#### Capabilities

Specifies the capabilities of the external transport. For example ED_TRANSCAP_CAN_EJECT, ED_TRANSCAP_CAN_PLAY_BACKWARDS, or ED_TRANSCAP_CAN_BUMP_PLAY. See Remarks.


#### SignalMode

Specifies the signal mode of the external transport. For example ED_TRANSBASIC_SIGNAL_525_60_SD, ED_TRANSBASIC_SIGNAL_MPEG2TS or ED_TRANSBASIC_SIGNAL_0625_50_MPEG. See Remarks


#### LoadMedium

Specifies load medium. For example eject, open tray, close tray.


#### MediumInfo

Describes the medium info.


#### XPrtState

Describes the external transports state.


#### Timecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


#### dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


#### dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.


#### RawAVC



### -field u.Timecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


#### Timecode.frame

Specifies the frame. This member is defined for future use.


#### Timecode.second

Specifies the second. This member is defined for future use.


#### Timecode.minute

Specifies the minute. This member is defined for future use.


#### Timecode.hour

Specifies the hour. This member is defined for future use.


### -field u.Timecode.frame

Specifies the frame. This member is defined for future use.


### -field u.Timecode.second

Specifies the second. This member is defined for future use.


### -field u.Timecode.minute

Specifies the minute. This member is defined for future use.


### -field u.Timecode.hour

Specifies the hour. This member is defined for future use.


### -field u.RawAVC



#### RawAVC.PayloadSize

Specifies the payload size.


#### RawAVC.Payload

Describes the payload


### -field u.RawAVC.PayloadSize

Specifies the payload size.


### -field u.RawAVC.Payload

Describes the payload


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


### -field u.dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.


### -field u.dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.


#### - NodeProperty

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.


## -remarks


Any ED_TRANSCAP_Xxx or ED_TRANSBASIC_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565168">KSPROPERTY_EXTXPORT_STATE</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-transport_state.md">TRANSPORT_STATE</a>

<a href="..\ksmedia\ns-ksmedia-medium_info.md">MEDIUM_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_EXTXPORT_NODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

