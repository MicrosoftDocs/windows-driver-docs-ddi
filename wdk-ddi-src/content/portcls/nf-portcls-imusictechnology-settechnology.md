---
UID: NF:portcls.IMusicTechnology.SetTechnology
title: IMusicTechnology::SetTechnology (portcls.h)
description: The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins.
old-location: audio\imusictechnology_settechnology.htm
tech.root: audio
ms.assetid: 7e32b408-930d-4ef4-960e-1a0da5ef6803
ms.date: 05/08/2018
keywords: ["IMusicTechnology::SetTechnology"]
ms.keywords: IMusicTechnology interface [Audio Devices],SetTechnology method, IMusicTechnology.SetTechnology, IMusicTechnology::SetTechnology, SetTechnology, SetTechnology method [Audio Devices], SetTechnology method [Audio Devices],IMusicTechnology interface, audio.imusictechnology_settechnology, audmp-routines_d1d6abaa-c4b8-4dce-8ce5-9fc12cc87852.xml, portcls/IMusicTechnology::SetTechnology
f1_keywords:
 - "portcls/IMusicTechnology.SetTechnology"
 - "IMusicTechnology.SetTechnology"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMusicTechnology.SetTechnology
targetos: Windows
req.typenames: 
---

# IMusicTechnology::SetTechnology


## -description


The <code>SetTechnology</code> method changes the <b>Technology</b> member of each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdatarange_music">KSDATARANGE_MUSIC</a> structure in the data ranges for the miniport driver's pins.


## -parameters




### -param Technology 
[in]
Specifies a technology GUID. This parameter should point to one of the GUIDs that are defined for the <b>Technology</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdatarange_music">KSDATARANGE_MUSIC</a> structure.


## -returns



<code>SetTechnology</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>SetTechology</code> method should be called before the miniport driver's <b>Init</b> method. If <code>SetTechnology</code> is not called, the miniport driver's <b>Technology</b> members are all set to KSMUSIC_TECHNOLOGY_PORT by default.

The following table lists the GUIDs that are defined for the <i>Technology</i> parameter and the corresponding integer value to which the <b>wTechnology</b> member of the MIDIOUTCAPS structure is set during a call to <b>midiOutGetDevCaps</b>.

<table>
<tr>
<th>Technology GUID</th>
<th>MIDIOUTCAPS.wTechnology</th>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_PORT

</td>
<td>
MOD_MIDIPORT

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_SQSYNTH

</td>
<td>
MOD_SQSYNTH

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_FMSYNTH 

</td>
<td>
MOD_FMSYNTH

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_WAVETABLE

</td>
<td>
MOD_WAVETABLE

</td>
</tr>
<tr>
<td>
KSMUSIC_TECHNOLOGY_SWSYNTH

</td>
<td>
MOD_SWSYNTH

</td>
</tr>
</table>
 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/music-technology-guids">Music Technology GUIDs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-imusictechnology">IMusicTechnology</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdatarange_music">KSDATARANGE_MUSIC</a>
 

 

