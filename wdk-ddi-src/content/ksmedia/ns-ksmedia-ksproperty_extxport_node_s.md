---
UID: NS:ksmedia.KSPROPERTY_EXTXPORT_NODE_S
title: KSPROPERTY_EXTXPORT_NODE_S
author: windows-driver-content
description: The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.
old-location: stream\ksproperty_extxport_node_s.htm
old-project: stream
ms.assetid: e0321fa8-610b-4920-8be8-dd91a3452beb
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S, KSPROPERTY_EXTXPORT_NODE_S structure [Streaming Media Devices], PKSPROPERTY_EXTXPORT_NODE_S, PKSPROPERTY_EXTXPORT_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_EXTXPORT_NODE_S, ksmedia/PKSPROPERTY_EXTXPORT_NODE_S, stream.ksproperty_extxport_node_s, vidcapstruct_06823ca7-5d41-494c-879e-0835ab0b447f.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSPROPERTY_EXTXPORT_NODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_EXTXPORT_NODE_S, *PKSPROPERTY_EXTXPORT_NODE_S
---

# KSPROPERTY_EXTXPORT_NODE_S structure


## -description


The KSPROPERTY_EXTXPORT_NODE_S structure describes an external transport and its capabilities.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.


### -field u



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



#### dwTimecode

Specifies the timecode, in hour:minute:second:frame format. This member is defined for future use.



#### dwAbsTrackNumber

Specifies the absolute track number. This member is defined for future use.


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


### -field u.RawAVC


### -field u.RawAVC.PayloadSize

Specifies the payload size.


### -field u.RawAVC.Payload

Describes the payload


## -remarks



Any ED_TRANSCAP_Xxx or ED_TRANSBASIC_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565168">KSPROPERTY_EXTXPORT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567726">MEDIUM_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568546">TRANSPORT_STATE</a>
 

 

