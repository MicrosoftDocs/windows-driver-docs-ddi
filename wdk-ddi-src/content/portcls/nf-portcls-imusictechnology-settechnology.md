---
UID: NF:portcls.IMusicTechnology.SetTechnology
title: IMusicTechnology::SetTechnology method
author: windows-driver-content
description: The SetTechnology method changes the Technology member of each KSDATARANGE_MUSIC structure in the data ranges for the miniport driver's pins.
old-location: audio\imusictechnology_settechnology.htm
old-project: audio
ms.assetid: 7e32b408-930d-4ef4-960e-1a0da5ef6803
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMusicTechnology, IMusicTechnology::SetTechnology, SetTechnology
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMusicTechnology.SetTechnology
req.alt-loc: portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMusicTechnology::SetTechnology method



## -description
The <code>SetTechnology</code> method changes the <b>Technology</b> member of each <a href="..\ksmedia\ns-ksmedia-ksdatarange_music.md">KSDATARANGE_MUSIC</a> structure in the data ranges for the miniport driver's pins.



## -syntax

````
NTSTATUS SetTechnology(
  [in] const GUID *Technology
);
````


## -parameters

### -param Technology [in]

Specifies a technology GUID. This parameter should point to one of the GUIDs that are defined for the <b>Technology</b> member of the <a href="..\ksmedia\ns-ksmedia-ksdatarange_music.md">KSDATARANGE_MUSIC</a> structure.


## -returns
<code>SetTechnology</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks
The <code>SetTechology</code> method should be called before the miniport driver's <b>Init</b> method. If <code>SetTechnology</code> is not called, the miniport driver's <b>Technology</b> members are all set to KSMUSIC_TECHNOLOGY_PORT by default.

The following table lists the GUIDs that are defined for the <i>Technology</i> parameter and the corresponding integer value to which the <b>wTechnology</b> member of the MIDIOUTCAPS structure is set during a call to <b>midiOutGetDevCaps</b>.

KSMUSIC_TECHNOLOGY_PORT

MOD_MIDIPORT

KSMUSIC_TECHNOLOGY_SQSYNTH

MOD_SQSYNTH

KSMUSIC_TECHNOLOGY_FMSYNTH 

MOD_FMSYNTH

KSMUSIC_TECHNOLOGY_WAVETABLE

MOD_WAVETABLE

KSMUSIC_TECHNOLOGY_SWSYNTH

MOD_SWSYNTH

For more information, see <a href="https://msdn.microsoft.com/3b7c2907-e67f-458e-809d-080dcc30be1a">Music Technology GUIDs</a>.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-imusictechnology.md">IMusicTechnology</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-ksdatarange_music.md">KSDATARANGE_MUSIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMusicTechnology::SetTechnology method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

