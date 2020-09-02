---
UID: NS:ksmedia.__unnamed_struct_9
title: KSAUDIO_MICROPHONE_COORDINATES (ksmedia.h)
description: The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array.
old-location: audio\ksaudio_microphone_coordinates.htm
tech.root: audio
ms.assetid: 443fb3c0-0e75-4abc-b44f-047752b3cab7
ms.date: 08/20/2020
keywords: ["KSAUDIO_MICROPHONE_COORDINATES structure"]
ms.keywords: "*PKSAUDIO_MICROPHONE_COORDINATES, KSAUDIO_MICROPHONE_COORDINATES, KSAUDIO_MICROPHONE_COORDINATES structure [Audio Devices], PKSAUDIO_MICROPHONE_COORDINATES, PKSAUDIO_MICROPHONE_COORDINATES structure pointer [Audio Devices], aud-prop_85a5f68f-13f2-4465-bb16-4d30e9c9d731.xml, audio.ksaudio_microphone_coordinates, ksmedia/KSAUDIO_MICROPHONE_COORDINATES, ksmedia/PKSAUDIO_MICROPHONE_COORDINATES"
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
req.typenames: KSAUDIO_MICROPHONE_COORDINATES, *PKSAUDIO_MICROPHONE_COORDINATES
f1_keywords:
 - PKSAUDIO_MICROPHONE_COORDINATES
 - ksmedia/PKSAUDIO_MICROPHONE_COORDINATES
 - KSAUDIO_MICROPHONE_COORDINATES
 - ksmedia/KSAUDIO_MICROPHONE_COORDINATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSAUDIO_MICROPHONE_COORDINATES
---

# KSAUDIO_MICROPHONE_COORDINATES structure


## -description

The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array.

## -struct-fields

### -field usType

Specifies the type of microphone in use at this coordinate location. The value of this member is one of the **KSMICARRAY_MICTYPE** enumeration values shown in the following table.

| Value | Microphone type |
|--|--|
| KSMICARRAY_MICTYPE_OMNIDIRECTIONAL | Omni directional |
| KSMICARRAY_MICTYPE_SUBCARDIOID | Sub cardioid |
| KSMICARRAY_MICTYPE_CARDIOID | Cardioid |
| KSMICARRAY_MICTYPE_SUPERCARDIOID | Super cardioid |
| KSMICARRAY_MICTYPE_HYPERCARDIOID | Hyper cardioid |
| KSMICARRAY_MICTYPE_8SHAPED | 8-shaped |
| KSMICARRAY_MICTYPE_VENDORDEFINED | 0x0F |

If the microphone is of type KSMICARRAY_MICTYPE_VENDORDEFINED, the value must be set to 0x0F. Additionally, the most significant bits will further define the type of microphone.

### -field wXCoord

Specifies the signed X-coordinate of the microphone, in millimeters. Acceptable values range from -32768 to 32767, inclusive.

### -field wYCoord

Specifies the signed Y-coordinate of the microphone, in millimeters. Acceptable values range from -32768 to 32767, inclusive.

### -field wZCoord

Specifies the signed Z-coordinate of the microphone, in millimeters. Acceptable values range from -32768 to 32767, inclusive.

### -field wVerticalAngle

Specifies a value between -15708 and +15708.  When divided by 10,000, it gives a radian angle measurement.

### -field wHorizontalAngle

Specifies a value between -31416 and +31416.  When divided by 10,000, it gives a radian angle measurement.

## -remarks

To better understand the descriptions for *wHorizontalAngle*  and *wVerticalAngle*, consider the following diagram:

![Diagram showing three microphones (Mic 1, Mic 2 and Mic 3) in an array. Mic 2 and Mic 3 are parallel to each other with their center lines parallel to the x axis, and with no vertical angle to their orientation. Mic 1  has a center line that is not parallel to the x axis and it also has a vertical angle to its orientation.](../images/audio-micarrayangles.png)

Let **x** be the axis which points from the center of the microphone array toward the most probable location of the user - that is, perpendicular to the screen.  Positive is toward the user, negative is behind the screen. Let **y** by the horizontal axis perpendicular to the x-axis - that is, from the left of the screen to the right.  Positive is to the user's right; negative is to the user's left. Let **z** be the vertical axis.

Now assume that there are three microphones in the array, as shown in the preceding diagram. And assume also, that one of the microphones (**Mic 1**) is pointed in a horizontal direction that is not parallel to the x-axis, as indicated by the blue center line through **Mic 1**. Now when you imagine a line that runs through the origin (0,0,0) of the (x,y,z) coordinate system and is parallel to the center line of **Mic 1**, you will find that there is a horizontal angle between the positive x-axis and the projection of the mic's center line onto the x-y plane. This angle is represented by *wHorizontalAngle*.

If one of the microphones, for example **Mic 1**, happens to be dipped downward, or raised up, then this microphone would also have a vertical angle between its center line and the projection of its center line onto the x-y plane. This angle is represented by *wVerticalAngle*.

For more information about how to process a microphone array in Windows, see the [Microphone array support in Windows](https://docs.microsoft.com/previous-versions/windows/hardware/design/dn613960(v=vs.85)) white paper.

