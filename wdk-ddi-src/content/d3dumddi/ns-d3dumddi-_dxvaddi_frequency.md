---
UID: NS:d3dumddi._DXVADDI_FREQUENCY
title: _DXVADDI_FREQUENCY (d3dumddi.h)
description: The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.
old-location: display\dxvaddi_frequency.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVADDI_FREQUENCY structure"]
ms.keywords: DXVA2_Structs_bf2ee217-d321-4302-8bd3-1621081fdb09.xml, DXVADDI_FREQUENCY, DXVADDI_FREQUENCY structure [Display Devices], _DXVADDI_FREQUENCY, d3dumddi/DXVADDI_FREQUENCY, display.dxvaddi_frequency
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXVADDI_FREQUENCY
f1_keywords:
 - _DXVADDI_FREQUENCY
 - d3dumddi/_DXVADDI_FREQUENCY
 - DXVADDI_FREQUENCY
 - d3dumddi/DXVADDI_FREQUENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _DXVADDI_FREQUENCY
 - DXVADDI_FREQUENCY
---

# _DXVADDI_FREQUENCY structure


## -description

The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.

## -struct-fields

### -field Numerator

[in] The numerator of the frequency fraction.

### -field Denominator

[in] The denominator of the frequency fraction.

## -remarks

The user-mode display driver must interpret the video frame rate for the following special cases as indicated:

<ul>
<li>
<b>Numerator</b>/<b>Denominator</b> = 0/0 is interpreted as an unknown frequency.

</li>
<li>
<b>Numerator</b>/<b>Denominator</b> = n/0, where n is any number, is interpreted as invalid.

</li>
<li>
<b>Numerator</b>/<b>Denominator</b> = 0/n is interpreted as zero frequency.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_videodesc">DXVADDI_VIDEODESC</a>

