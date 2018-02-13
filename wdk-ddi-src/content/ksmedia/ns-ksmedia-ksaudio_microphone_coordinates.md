---
UID: NS:ksmedia.KSAUDIO_MICROPHONE_COORDINATES
title: KSAUDIO_MICROPHONE_COORDINATES
author: windows-driver-content
description: The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array.
old-location: audio\ksaudio_microphone_coordinates.htm
old-project: audio
ms.assetid: 443fb3c0-0e75-4abc-b44f-047752b3cab7
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: KSAUDIO_MICROPHONE_COORDINATES, PKSAUDIO_MICROPHONE_COORDINATES, *PKSAUDIO_MICROPHONE_COORDINATES, aud-prop_85a5f68f-13f2-4465-bb16-4d30e9c9d731.xml, audio.ksaudio_microphone_coordinates, KSAUDIO_MICROPHONE_COORDINATES structure [Audio Devices], ksmedia/PKSAUDIO_MICROPHONE_COORDINATES, PKSAUDIO_MICROPHONE_COORDINATES structure pointer [Audio Devices], ksmedia/KSAUDIO_MICROPHONE_COORDINATES
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
-	KSAUDIO_MICROPHONE_COORDINATES
product: Windows
targetos: Windows
req.typenames: "*PKSAUDIO_MICROPHONE_COORDINATES, KSAUDIO_MICROPHONE_COORDINATES"
---

# KSAUDIO_MICROPHONE_COORDINATES structure


## -description


The KSAUDIO_MICROPHONE_COORDINATES structure specifies the type and the coordinates of a single microphone in the microphone array.


## -syntax


````
typedef struct {
  USHORT usType;
  SHORT  wXCoord;
  SHORT  wYCoord;
  SHORT  wZCoord;
  SHORT  wVerticalAngle;
  SHORT  wHorizontalAngle;
} KSAUDIO_MICROPHONE_COORDINATES, *PKSAUDIO_MICROPHONE_COORDINATES;
````


## -struct-fields




### -field usType

Specifies the type of microphone in use at this coordinate location. The value of this member is one of the <b>KSMICARRAY_MICTYPE</b> enumeration values shown in the following table.

<table>
<tr>
<td>
<b>Value</b>

</td>
<td>
<b>Microphone type</b>

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_OMNIDIRECTIONAL

</td>
<td>
Omni directional

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_SUBCARDIOID

</td>
<td>
Sub cardioid

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_CARDIOID

</td>
<td>
Cardioid

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_SUPERCARDIOID

</td>
<td>
Super cardioid

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_HYPERCARDIOID

</td>
<td>
Hyper cardioid

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_8SHAPED

</td>
<td>
8-shaped

</td>
</tr>
<tr>
<td>
KSMICARRAY_MICTYPE_VENDORDEFINED

</td>
<td>
0x0F

</td>
</tr>
</table>
 

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



To better understand the descriptions for <i>wHorizontalAngle</i>  and <i>wVericalAngle</i>, consider the following diagram:

<img alt="Diagram showing three microphones (Mic 1, Mic 2 and Mic 3) in an array. Mic 2 and Mic 3 are parallel to each other with their center lines parallel to the x axis, and with no vertical angle to their orientation. Mic 1  has a center line that is not parallel to the x axis and it also has a vertical angle to its orientation." src="images/MicArrayAngles.png"/>
Let <b>x</b> be the axis which points from the center of the microphone array toward the most probable location of the user - that is, perpendicular to the screen.  Positive is toward the user, negative is behind the screen. Let <b>y</b> by the horizontal axis perpendicular to the x-axis - that is, from the left of the screen to the right.  Positive is to the user's right; negative is to the user's left. Let <b>z</b> be the vertical axis.

Now assume that there are three microphones in the array, as shown in the preceding diagram. And assume also, that one of the microphones (<b>Mic 1</b>) is pointed in a horizontal direction that is not parallel to the x-axis, as indicated by the blue center line through <b>Mic 1</b>. Now when you imagine a line that runs through the origin (0,0,0) of the (x,y,z) coordinate system and is parallel to the center line of <b>Mic 1</b>, you will find that there is a horizontal angle between the positive x-axis and the projection of the mic’s center line onto the x-y plane. This angle is represented by <i>wHorizontalAngle</i>.

If one of the microphones, for example <b>Mic 1</b>, happens to be dipped downward, or raised up, then this microphone would also have a vertical angle between its center line and the projection of its center line onto the x-y plane. This angle is represented by <i>wVericalAngle</i>.

For more information about how to process a microphone array in Windows, see <a href="http://go.microsoft.com/fwlink/p/?linkid=8751">Audio Technologies for Windows </a> and refer to the following white papers:

<a href="http://go.microsoft.com/fwlink/p/?linkid=120592">Microphone Array Support in Windows Vista</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=120593">How to Build and Use Microphone Arrays for Windows Vista</a>



