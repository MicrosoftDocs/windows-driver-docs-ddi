---
UID: NS:ksmedia.KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
title: KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
author: windows-driver-content
description: The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device.
old-location: stream\ksproperty_videocompression_getinfo_s.htm
old-project: stream
ms.assetid: a34f051e-9769-427e-b1a7-2718a023e9d1
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure [Streaming Media Devices], PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, ksmedia/PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, stream.ksproperty_videocompression_getinfo_s, vidcapstruct_28f47a4f-d28e-40b4-acc5-42835ec89b40.xml"
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
-	KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S, *PKSPROPERTY_VIDEOCOMPRESSION_GETINFO_S
---

# KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure


## -description


The KSPROPERTY_VIDEOCOMPRESSION_GETINFO_S structure describes information about the video compression capabilities supported by a device.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field StreamIndex

Specifies the zero-based index of the stream being queried.


### -field DefaultKeyFrameRate

Indicates the estimated number of frames per key frame.


### -field DefaultPFrameRate

Indicates the predicted number of frames per key frame.


### -field DefaultQuality

Specifies the default quality value. This value should be in the range from 0 through 10000. 


### -field NumberOfQualitySettings

Indicates the number of discrete compression quality settings the device supports.


### -field Capabilities

Specifies the compression capabilities of the device. This member can be one or more (logically ORed) of the values from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567313">KS_CompressionCaps</a> enumeration.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567313">KS_CompressionCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567813">PROPSETID_VIDCAP_VIDEOCOMPRESSION</a>
 

 

