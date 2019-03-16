---
UID: NS:ksmedia.__unnamed_struct_13
title: KSDS3D_BUFFER_ALL (ksmedia.h)
description: The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.
old-location: audio\ksds3d_buffer_all.htm
tech.root: audio
ms.assetid: c94e2189-62a6-44d6-9a29-4fd32c72437a
ms.date: 05/08/2018
ms.keywords: "*PKSDS3D_BUFFER_ALL, KSDS3D_BUFFER_ALL, KSDS3D_BUFFER_ALL structure [Audio Devices], PKSDS3D_BUFFER_ALL, PKSDS3D_BUFFER_ALL structure pointer [Audio Devices], aud-prop_46bd2b81-3d2a-49e1-93e6-867e84ae4c04.xml, audio.ksds3d_buffer_all, ksmedia/KSDS3D_BUFFER_ALL, ksmedia/PKSDS3D_BUFFER_ALL"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSDS3D_BUFFER_ALL
product:
- Windows
targetos: Windows
req.typenames: KSDS3D_BUFFER_ALL, *PKSDS3D_BUFFER_ALL
---

# KSDS3D_BUFFER_ALL structure


## -description


The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.


## -struct-fields




### -field Position

Specifies the x, y, and z position coordinates of the 3D sound buffer. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536367">DS3DVECTOR</a>.


### -field Velocity

Specifies the x, y, and z velocity components of the 3D sound buffer. This member is a structure of type DS3DVECTOR.


### -field InsideConeAngle

Specifies the angle in degrees of the inside sound projection cone.


### -field OutsideConeAngle

Specifies the angle in degrees of the outside sound projection cone.


### -field ConeOrientation

Specifies the x, y, and z components of the orientation of the 3D buffer's sound projection cone. This member is a structure of type DS3DVECTOR.


### -field ConeOutsideVolume

Specifies the cone outside volume.


### -field MinDistance

Specifies the minimum distance between the speaker and listener. (See the discussion of minimum and maximum distances for DirectSound 3D buffers in the Microsoft Windows SDK documentation.)


### -field MaxDistance

Specifies the maximum distance between the speaker and listener.


### -field Mode

Specifies the 3D sound-processing mode. This can be one of the following values from the header file Dsound.h:

<ul>
<li>
DS3DMODE_DISABLE 

</li>
<li>
DS3DMODE_HEADRELATIVE 

</li>
<li>
DS3DMODE_NORMAL

</li>
</ul>
For the meaning of these parameters, see the description of the <b>dwMode</b> member of the DS3DBUFFER structure in the Microsoft Windows SDK documentation.


## -remarks



This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a> property. DirectSound uses this property to implement the <b>IDirectSound3DBuffer::GetAllParameters</b> and <b>IDirectSound3DBuffer::SetAllParameters</b> methods, which are described in the Windows SDK documentation.

The members of this structure are similar to those defined for the DS3DBUFFER structure in the Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536367">DS3DVECTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a>
 

 

