---
UID: NS:ksmedia._DS3DVECTOR
title: _DS3DVECTOR (ksmedia.h)
description: The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components.
old-location: audio\ds3dvector.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["DS3DVECTOR structure"]
ms.keywords: "*PDS3DVECTOR, DS3DVECTOR, DS3DVECTOR structure [Audio Devices], PDS3DVECTOR, PDS3DVECTOR structure pointer [Audio Devices], _DS3DVECTOR, aud-prop_3e17b5ec-c2fc-4e6c-bff1-27be36e376c9.xml, audio.ds3dvector, ksmedia/DS3DVECTOR, ksmedia/PDS3DVECTOR"
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
req.typenames: DS3DVECTOR, *PDS3DVECTOR
f1_keywords:
 - _DS3DVECTOR
 - ksmedia/_DS3DVECTOR
 - PDS3DVECTOR
 - ksmedia/PDS3DVECTOR
 - DS3DVECTOR
 - ksmedia/DS3DVECTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - DS3DVECTOR
---

# _DS3DVECTOR structure


## -description

The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components.

## -struct-fields

### -field x

Specifies the x-coordinate of the position.

### -field dvX

Specifies the x-component of the vector.

### -field y

Specifies the y-coordinate of the position.

### -field dvY

Specifies the y-component of the vector.

### -field z

Specifies the z-coordinate of the position.

### -field dvZ

Specifies the z-component of the vector.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_buffer_all">KSDS3D_BUFFER_ALL</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_listener_all">KSDS3D_LISTENER_ALL</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksds3d_listener_orientation">KSDS3D_LISTENER_ORIENTATION</a>
