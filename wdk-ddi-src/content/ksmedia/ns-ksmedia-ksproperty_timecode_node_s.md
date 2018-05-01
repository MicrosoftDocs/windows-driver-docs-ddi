---
UID: NS:ksmedia.KSPROPERTY_TIMECODE_NODE_S
title: KSPROPERTY_TIMECODE_NODE_S
author: windows-driver-content
description: The KSPROPERTY_TIMECODE_NODE_S structure describes a timecode.
old-location: stream\ksproperty_timecode_node_s.htm
old-project: stream
ms.assetid: deb218b4-4478-46f6-9859-c1a6d7b73784
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_TIMECODE_NODE_S, KSPROPERTY_TIMECODE_NODE_S, KSPROPERTY_TIMECODE_NODE_S structure [Streaming Media Devices], PKSPROPERTY_TIMECODE_NODE_S, PKSPROPERTY_TIMECODE_NODE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_TIMECODE_NODE_S, ksmedia/PKSPROPERTY_TIMECODE_NODE_S, stream.ksproperty_timecode_node_s, vidcapstruct_3c1b784a-1cd7-40b8-a0af-35c60b02cc50.xml"
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
-	KSPROPERTY_TIMECODE_NODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TIMECODE_NODE_S, *PKSPROPERTY_TIMECODE_NODE_S
---

# KSPROPERTY_TIMECODE_NODE_S structure


## -description


The KSPROPERTY_TIMECODE_NODE_S structure describes a timecode.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff566720">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.


### -field TimecodeSamp

Specifies the timecode sample. Timecode, absolute track number (ATN) and relative time counter (RTC) are in the <b>TimecodeSamp.timecode.dwFrames</b> member.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565781">KSPROPERTY_TIMECODE_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568528">TIMECODE_SAMPLE</a>
 

 

