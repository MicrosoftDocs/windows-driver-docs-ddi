---
UID: NS:d3dumddi._DDRAW_CAPS
title: _DDRAW_CAPS
author: windows-driver-content
description: The DDRAW_CAPS structure describes general Microsoft DirectDraw capabilities that the user-mode display driver supports.
old-location: display\ddraw_caps.htm
old-project: display
ms.assetid: 023e3780-bc88-446b-b235-8853807fb05a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DDRAW_CAPS, DDRAW_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DDRAW_CAPS
req.alt-loc: d3dumddi.h
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
req.typenames: DDRAW_CAPS
---

# _DDRAW_CAPS structure



## -description
The DDRAW_CAPS structure describes general Microsoft DirectDraw capabilities that the user-mode display driver supports.



## -syntax

````
typedef struct _DDRAW_CAPS {
  UINT Caps;
  UINT Caps2;
  UINT CKeyCaps;
  UINT FxCaps;
  UINT MaxVideoPorts;
} DDRAW_CAPS;
````


## -struct-fields

### -field Caps

[out] A valid bitwise OR of the following general capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDRAW_CAPS_ZBLTS

</td>
<td>
Z-buffers can be used in bit-block transfer (bitblt) operations.

</td>
</tr>
<tr>
<td>
DDRAW_CAPS_COLORKEY

</td>
<td>
Some form of color key can be used in either overlay or bitblt operations. For more specific color key capability information, see the <b>CKeyCaps</b> member.

</td>
</tr>
<tr>
<td>
DDRAW_CAPS_BLTDEPTHFILL

</td>
<td>
Z-buffers can be depth-filled in bitblt operations.

</td>
</tr>
</table>
 


### -field Caps2

[out] A valid bitwise OR of more of the following general capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDRAW_CAPS2_VIDEOPORT

</td>
<td>
A hardware video port can be used.

</td>
</tr>
<tr>
<td>
DDRAW_CAPS2_CANDROPZ16BIT

</td>
<td>
Sixteen-bit RGBZ values can be converted into 16-bit RGB values. (The system does not support 8-bit conversions.)

</td>
</tr>
<tr>
<td>
DDRAW_CAPS2_FLIPINTERVAL

</td>
<td>
The driver responds to the <b>Flip</b> bit-field flag.

</td>
</tr>
<tr>
<td>
DDRAW_CAPS2_FLIPNOVSYNC

</td>
<td>
The driver responds to the <b>FlipWithNoWait</b> bit-field flag.

</td>
</tr>
<tr>
<td>
DDRAW_CAPS2_DYNAMICTEXTURES

</td>
<td>
The driver supports dynamic textures.

</td>
</tr>
</table>
 


### -field CKeyCaps

[out] A valid bitwise OR of the following color key capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDRAW_CKEYCAPS_SRCBLT

</td>
<td>
Transparent bit-block transfers can be performed with a color key that identifies bits of the source surface that are copied to the destination surface.

</td>
</tr>
<tr>
<td>
DDRAW_CKEYCAPS_DESTBLT

</td>
<td>
Transparent bit-block transfers (bitblts) can be performed with a color key that identifies the replaceable bits of the destination surface.

</td>
</tr>
</table>
 


### -field FxCaps

[out] A valid bitwise OR of the following stretching and effects capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DDRAW_FXCAPS_BLTMIRRORLEFTRIGHT

</td>
<td>
Bit-block transfers (bitblts) that flip the contents of the source surface to the destination surface horizontally along the center axis can be performed.

</td>
</tr>
<tr>
<td>
DDRAW_FXCAPS_BLTMIRRORUPDOWN

</td>
<td>
Bit-block transfers (bitblts) that flip the contents of the source surface to the destination surface vertically along the center axis can be performed.

</td>
</tr>
</table>
 


### -field MaxVideoPorts

[out] The maximum number of video ports that the device supports.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDRAW_CAPS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

