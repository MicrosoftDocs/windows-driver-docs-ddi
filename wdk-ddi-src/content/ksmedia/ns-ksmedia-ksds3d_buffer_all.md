---
UID: NS:ksmedia.KSDS3D_BUFFER_ALL
title: KSDS3D_BUFFER_ALL
author: windows-driver-content
description: The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.
old-location: audio\ksds3d_buffer_all.htm
old-project: audio
ms.assetid: c94e2189-62a6-44d6-9a29-4fd32c72437a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PKSDS3D_BUFFER_ALL, *PKSDS3D_BUFFER_ALL, ksmedia/PKSDS3D_BUFFER_ALL, PKSDS3D_BUFFER_ALL structure pointer [Audio Devices], aud-prop_46bd2b81-3d2a-49e1-93e6-867e84ae4c04.xml, KSDS3D_BUFFER_ALL structure [Audio Devices], ksmedia/KSDS3D_BUFFER_ALL, audio.ksds3d_buffer_all, KSDS3D_BUFFER_ALL
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
-	KSDS3D_BUFFER_ALL
product: Windows
targetos: Windows
req.typenames: "*PKSDS3D_BUFFER_ALL, KSDS3D_BUFFER_ALL"
---

# KSDS3D_BUFFER_ALL structure


## -description


The KSDS3D_BUFFER_ALL structure specifies all the 3D characteristics of a DirectSound 3D buffer.


## -syntax


````
typedef struct {
  DS3DVECTOR Position;
  DS3DVECTOR Velocity;
  ULONG      InsideConeAngle;
  ULONG      OutsideConeAngle;
  DS3DVECTOR ConeOrientation;
  LONG       ConeOutsideVolume;
  FLOAT      MinDistance;
  FLOAT      MaxDistance;
  ULONG      Mode;
} KSDS3D_BUFFER_ALL, *PKSDS3D_BUFFER_ALL;
````


## -struct-fields




#### - Position

Specifies the x, y, and z position coordinates of the 3D sound buffer. This member is a structure of type <a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>.


#### - Velocity

Specifies the x, y, and z velocity components of the 3D sound buffer. This member is a structure of type DS3DVECTOR.


#### - InsideConeAngle

Specifies the angle in degrees of the inside sound projection cone.


#### - OutsideConeAngle

Specifies the angle in degrees of the outside sound projection cone.


#### - ConeOrientation

Specifies the x, y, and z components of the orientation of the 3D buffer's sound projection cone. This member is a structure of type DS3DVECTOR.


#### - ConeOutsideVolume

Specifies the cone outside volume.


#### - MinDistance

Specifies the minimum distance between the speaker and listener. (See the discussion of minimum and maximum distances for DirectSound 3D buffers in the Microsoft Windows SDK documentation.)


#### - MaxDistance

Specifies the maximum distance between the speaker and listener.


#### - Mode

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
</ul>For the meaning of these parameters, see the description of the <b>dwMode</b> member of the DS3DBUFFER structure in the Microsoft Windows SDK documentation.


## -remarks


This structure is used to set or get the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a> property. DirectSound uses this property to implement the <b>IDirectSound3DBuffer::GetAllParameters</b> and <b>IDirectSound3DBuffer::SetAllParameters</b> methods, which are described in the Windows SDK documentation.

The members of this structure are similar to those defined for the DS3DBUFFER structure in the Windows SDK documentation.



## -see-also

<a href="..\ksmedia\ns-ksmedia-_ds3dvector.md">DS3DVECTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537315">KSPROPERTY_DIRECTSOUND3DBUFFER_ALL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_BUFFER_ALL structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

