---
UID: NS:ksmedia.KSDS3D_BUFFER_CONE_ANGLES
title: KSDS3D_BUFFER_CONE_ANGLES
author: windows-driver-content
description: A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles.
old-location: audio\ksds3d_buffer_cone_angles.htm
old-project: audio
ms.assetid: 702d3698-396d-4609-a082-74290d2ccb41
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PKSDS3D_BUFFER_CONE_ANGLES structure pointer [Audio Devices], audio.ksds3d_buffer_cone_angles, KSDS3D_BUFFER_CONE_ANGLES structure [Audio Devices], ksmedia/PKSDS3D_BUFFER_CONE_ANGLES, KSDS3D_BUFFER_CONE_ANGLES, PKSDS3D_BUFFER_CONE_ANGLES, ksmedia/KSDS3D_BUFFER_CONE_ANGLES, aud-prop_6b484499-7859-4c81-828d-35c2dc0dc070.xml, *PKSDS3D_BUFFER_CONE_ANGLES
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
-	KSDS3D_BUFFER_CONE_ANGLES
product: Windows
targetos: Windows
req.typenames: KSDS3D_BUFFER_CONE_ANGLES, *PKSDS3D_BUFFER_CONE_ANGLES
---

# KSDS3D_BUFFER_CONE_ANGLES structure


## -description


A KSDS3D_BUFFER_CONE_ANGLES structure specifies the inside and outside cone angles.


## -syntax


````
typedef struct {
  ULONG InsideConeAngle;
  ULONG OutsideConeAngle;
} KSDS3D_BUFFER_CONE_ANGLES, *PKSDS3D_BUFFER_CONE_ANGLES;
````


## -struct-fields




### -field InsideConeAngle

Specifies the angle in degrees of the inside sound projection cone.


### -field OutsideConeAngle

Specifies the angle in degrees of the outside sound projection cone.


## -remarks


This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537318">KSPROPERTY_DIRECTSOUND3DBUFFER_CONEANGLES</a> property. DirectSound uses this property to implement the <b>IDirectSound3DBuffer::GetConeAngles</b> and <b>IDirectSound3DBuffer::SetConeAngles</b> methods, which are described in the Microsoft Windows SDK documentation.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537318">KSPROPERTY_DIRECTSOUND3DBUFFER_CONEANGLES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_BUFFER_CONE_ANGLES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

