---
UID: NS:ksmedia.KSRTAUDIO_GETREADPACKET_INFO
title: KSRTAUDIO_GETREADPACKET_INFO
author: windows-driver-content
description: The KSRTAUDIO_GETREADPACKET_INFO structure describes information for an audio packet.
old-location: audio\ksrtaudio_getreadpacket_info.htm
tech.root: audio
ms.assetid: 0157FA09-C227-4BB2-BB75-0AB5802BC150
ms.date: 05/08/2018
ms.keywords: "*PKSRTAUDIO_GETREADPACKET_INFO, KSRTAUDIO_GETREADPACKET_INFO, KSRTAUDIO_GETREADPACKET_INFO structure [Audio Devices], PKSRTAUDIO_GETREADPACKET_INFO, PKSRTAUDIO_GETREADPACKET_INFO structure pointer [Audio Devices], audio.ksrtaudio_getreadpacket_info, ksmedia/KSRTAUDIO_GETREADPACKET_INFO, ksmedia/PKSRTAUDIO_GETREADPACKET_INFO"
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later Windows operating systems.
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
-	KSRTAUDIO_GETREADPACKET_INFO
product:
- Windows
targetos: Windows
req.typenames: KSRTAUDIO_GETREADPACKET_INFO, *PKSRTAUDIO_GETREADPACKET_INFO
---

# KSRTAUDIO_GETREADPACKET_INFO structure


## -description


The KSRTAUDIO_GETREADPACKET_INFO structure describes information for an audio packet.


## -struct-fields




### -field PacketNumber

Returns the packet number relative to the start of capture. 


### -field Flags

Reserved for future use. Must be set to 0. 


### -field PerformanceCounterValue

Returns the performance counter value corresponding to the sampling instant of the first sample in the packet. 


### -field MoreData

Returns TRUE if there is more data ready immediately. The OS may optionally immediately call this routine again after processing the packet to get the next packet information. If the driver returns FALSE, then capture is operating at real time. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt786974">KSPROPERTY_RTAUDIO_GETREADPACKET</a>
 

 

