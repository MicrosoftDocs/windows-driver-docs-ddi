---
UID: NS:ksmedia.KSPROPERTY_TIMECODE_NODE_S
title: KSPROPERTY_TIMECODE_NODE_S
author: windows-driver-content
description: The KSPROPERTY_TIMECODE_NODE_S structure describes a timecode.
old-location: stream\ksproperty_timecode_node_s.htm
old-project: stream
ms.assetid: deb218b4-4478-46f6-9859-c1a6d7b73784
ms.author: windowsdriverdev
ms.date: 2/23/2018
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


## -syntax


````
typedef struct {
  KSP_NODE        NodeProperty;
  TIMECODE_SAMPLE TimecodeSamp;
} KSPROPERTY_TIMECODE_NODE_S, *PKSPROPERTY_TIMECODE_NODE_S;
````


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the property set, property ID, request type, and node ID.


### -field TimecodeSamp

Specifies the timecode sample. Timecode, absolute track number (ATN) and relative time counter (RTC) are in the <b>TimecodeSamp.timecode.dwFrames</b> member.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_timecode_s.md">KSPROPERTY_TIMECODE_S</a>



<a href="..\ksmedia\ns-ksmedia-tagtimecode_sample.md">TIMECODE_SAMPLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TIMECODE_NODE_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

