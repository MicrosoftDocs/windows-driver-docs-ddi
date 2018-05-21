---
UID: NS:ks.KSPROPERTY_POSITIONS
title: KSPROPERTY_POSITIONS
author: windows-driver-content
description: The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.
old-location: stream\ksproperty_positions.htm
old-project: stream
ms.assetid: 869d3a3f-e2f8-4c23-864b-d40f3e67a9ec
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS structure [Streaming Media Devices], PKSPROPERTY_POSITIONS, PKSPROPERTY_POSITIONS structure pointer [Streaming Media Devices], ks-struct_97829290-4c01-4a03-b56b-3e5915941094.xml, ks/KSPROPERTY_POSITIONS, ks/PKSPROPERTY_POSITIONS, stream.ksproperty_positions"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSPROPERTY_POSITIONS
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS
---

# KSPROPERTY_POSITIONS structure


## -description


The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.


## -struct-fields




### -field Current

Specifies the current position as a 64-bit value.


### -field Stop

Specifies the stop position as a 64-bit value.


### -field CurrentFlags

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567677">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Current</b> parameter.


### -field StopFlags

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff567677">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Stop</b> parameter.


## -remarks



The KSPROPERTY_POSITIONS structure is used with positioning properties in the KSPROPSETID_MediaSeeking property set. These properties correspond to DirectShow's <b>IMediaSeeking::GetPositions</b> and <b>IMediaSeeking::SetPositions</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565185">KSPROPERTY_MEDIASEEKING_POSITIONS</a>
 

 

