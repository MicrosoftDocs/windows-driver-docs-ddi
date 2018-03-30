---
UID: NS:ksmedia.KSDS3D_BUFFER_CONE_ANGLES
title: KSDS3D_BUFFER_CONE_ANGLES
author: windows-driver-content
description: A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles.
old-location: audio\ksds3d_buffer_cone_angles.htm
old-project: audio
ms.assetid: 702d3698-396d-4609-a082-74290d2ccb41
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSDS3D_BUFFER_CONE_ANGLES, KSDS3D_BUFFER_CONE_ANGLES, KSDS3D_BUFFER_CONE_ANGLES structure [Audio Devices], PKSDS3D_BUFFER_CONE_ANGLES, PKSDS3D_BUFFER_CONE_ANGLES structure pointer [Audio Devices], aud-prop_6b484499-7859-4c81-828d-35c2dc0dc070.xml, audio.ksds3d_buffer_cone_angles, ksmedia/KSDS3D_BUFFER_CONE_ANGLES, ksmedia/PKSDS3D_BUFFER_CONE_ANGLES"
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
-	KSDS3D_BUFFER_CONE_ANGLES
product: Windows
targetos: Windows
req.typenames: KSDS3D_BUFFER_CONE_ANGLES, *PKSDS3D_BUFFER_CONE_ANGLES
---

# KSDS3D_BUFFER_CONE_ANGLES structure


## -description


A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles.


## -struct-fields




### -field InsideConeAngle

Specifies the angle in degrees of the inside sound projection cone.


### -field OutsideConeAngle

Specifies the angle in degrees of the outside sound projection cone.


## -remarks



This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537318">KSPROPERTY_DIRECTSOUND3DBUFFER_CONEANGLES</a> property. DirectSound uses this property to implement the <b>IDirectSound3DBuffer::GetConeAngles</b> and <b>IDirectSound3DBuffer::SetConeAngles</b> methods, which are described in the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537318">KSPROPERTY_DIRECTSOUND3DBUFFER_CONEANGLES</a>
 

 

