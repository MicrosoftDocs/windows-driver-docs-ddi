---
UID: NS:ksmedia.__unnamed_struct_12
title: KSDS3D_LISTENER_ORIENTATION (ksmedia.h)
description: A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION property.
old-location: audio\ksds3d_listener_orientation.htm
tech.root: audio
ms.assetid: 3bcb9a6f-aacc-4b42-ba8e-1a1a4898f96d
ms.date: 05/08/2018
keywords: ["KSDS3D_LISTENER_ORIENTATION structure"]
ms.keywords: "*PKSDS3D_LISTENER_ORIENTATION, KSDS3D_LISTENER_ORIENTATION, KSDS3D_LISTENER_ORIENTATION structure [Audio Devices], PKSDS3D_LISTENER_ORIENTATION, PKSDS3D_LISTENER_ORIENTATION structure pointer [Audio Devices], aud-prop_9e525f5b-c264-46e5-84f3-3a7845b61200.xml, audio.ksds3d_listener_orientation, ksmedia/KSDS3D_LISTENER_ORIENTATION, ksmedia/PKSDS3D_LISTENER_ORIENTATION"
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
targetos: Windows
req.typenames: KSDS3D_LISTENER_ORIENTATION, *PKSDS3D_LISTENER_ORIENTATION
f1_keywords:
 - PKSDS3D_LISTENER_ORIENTATION
 - ksmedia/PKSDS3D_LISTENER_ORIENTATION
 - KSDS3D_LISTENER_ORIENTATION
 - ksmedia/KSDS3D_LISTENER_ORIENTATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSDS3D_LISTENER_ORIENTATION
---

# KSDS3D_LISTENER_ORIENTATION structure


## -description

A KSD3D_LISTENER_ORIENTATION structure specifies the position vector of the 3D listener. This structure is used to get or set the data value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-directsound3dlistener-orientation">KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION</a> property.

## -struct-fields

### -field Front

Specifies the front orientation vector of the 3D listener. This member is a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ds3dvector">DS3DVECTOR</a>.

### -field Top

Specifies the top orientation vector of the 3D listener. This member is a structure of type DS3DVECTOR.

## -remarks

DirectSound uses this property to implement the <b>IDirectSound3DListener::GetOrientation</b> and <b>IDirectSound3DListener::SetOrientation</b> methods, which are described in the Microsoft Windows SDK documentation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-_ds3dvector">DS3DVECTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-directsound3dlistener-orientation">KSPROPERTY_DIRECTSOUND3DLISTENER_ORIENTATION</a>

