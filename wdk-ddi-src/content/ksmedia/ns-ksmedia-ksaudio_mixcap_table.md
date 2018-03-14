---
UID: NS:ksmedia.KSAUDIO_MIXCAP_TABLE
title: KSAUDIO_MIXCAP_TABLE
author: windows-driver-content
description: The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node (KSNODETYPE_SUPERMIX). This structure is used to get or set the data value for the KSPROPERTY_AUDIO_MIX_LEVEL_CAPS property.
old-location: audio\ksaudio_mixcap_table.htm
old-project: audio
ms.assetid: 508d73f6-1660-4663-87f5-8dbd1dff153a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSAUDIO_MIXCAP_TABLE, KSAUDIO_MIXCAP_TABLE, KSAUDIO_MIXCAP_TABLE structure [Audio Devices], PKSAUDIO_MIXCAP_TABLE, PKSAUDIO_MIXCAP_TABLE structure pointer [Audio Devices], aud-prop_42fdfffa-fb37-4a29-8015-065cec552815.xml, audio.ksaudio_mixcap_table, ksmedia/KSAUDIO_MIXCAP_TABLE, ksmedia/PKSAUDIO_MIXCAP_TABLE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSAUDIO_MIXCAP_TABLE
product: Windows
targetos: Windows
req.typenames: KSAUDIO_MIXCAP_TABLE, *PKSAUDIO_MIXCAP_TABLE
---

# KSAUDIO_MIXCAP_TABLE structure


## -description


The KSAUDIO_MIXCAP_TABLE structure specifies the mixing capabilities of a supermixer node (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537198">KSNODETYPE_SUPERMIX</a>). This structure is used to get or set the data value for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537291">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a> property.


## -syntax


````
typedef struct {
  ULONG            InputChannels;
  ULONG            OutputChannels;
  KSAUDIO_MIX_CAPS Capabilities[1];
} KSAUDIO_MIXCAP_TABLE, *PKSAUDIO_MIXCAP_TABLE;
````


## -struct-fields




### -field InputChannels

Specifies the number of input channels.


### -field OutputChannels

Specifies the number of output channels.


### -field Capabilities

Contains the first entry in a two-dimensional array of <a href="..\ksmedia\ns-ksmedia-ksaudio_mix_caps.md">KSAUDIO_MIX_CAPS</a> structures. Given a supermixer node with <i>m</i> input channels and <i>n</i> output channels, the array contains <i>m</i>*<i></i> elements. Each element describes the mix-level capabilities of the path from a particular input channel to a particular output channel.


## -remarks



The <b>Capabilities</b> table is stored as a two-dimensional array:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  KSAUDIO_MIX_CAPS Capabilities[M*N];</pre>
</td>
</tr>
</table></span></div>
The table is an M-by-N matrix that maps M input channels into N output channels. The following table shows the mapping of <b>Capabilities</b> array elements to the supermixer node's M*N input-output paths.

<table>
<tr>
<th>Array element</th>
<th>Input-output path</th>
</tr>
<tr>
<td>
<b>Capabilities</b>[0]

</td>
<td>
Input channel 0 to output channel 0

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[1]

</td>
<td>
Input channel 0 to output channel 1

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[N-1]

</td>
<td>
Input channel 0 to output channel N-1

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[N]

</td>
<td>
Input channel 1 to output channel 0

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[N+1]

</td>
<td>
Input channel 1 to output channel 1

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[2N-1]

</td>
<td>
Input channel 1 to output channel N-1

</td>
</tr>
<tr>
<td>
<b>Capabilities</b>[M*N-1]

</td>
<td>
Input channel M-1 to output channel N-1

</td>
</tr>
</table>
 

In other words, the mixer caps for the path from input channel <i>i</i> to output channel <i>j</i> are contained in <b>Capabilities</b>[<i>i</i>*N+<i>j</i>]. If no path exists from input <i>i</i> to output <i>j</i>, set the <b>Mute</b> member of matrix element (<i>i</i>,<i>j</i>) to <b>TRUE</b>.

The size of the table is calculated from the KSAUDIO_MIXCAP_TABLE structure that is retrieved by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537291">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a> get property request. If the structure's <b>InputChannels</b> and <b>OutputChannels</b> members have the values <i>m</i> and <i>n</i>, the total storage required for the KSAUDIO_MIXCAP_TABLE structure plus the KSAUDIO_MIX_CAPS array is calculated as

<b>sizeof</b>(KSAUDIO_MIXCAP_TABLE) + (<i>m</i>*<i>n</i> - 1)*<b>sizeof</b>(KSAUDIO_MIX_CAPS)

If the client sends an initial KSPROPERTY_AUDIO_MIX_LEVEL_CAPS request in which the property size is specified as 2*<b>sizeof</b>(ULONG), the miniport driver should fill in only the first two members of the KSAUDIO_MIXCAP_TABLE structure, <b>InputChannels</b> and <b>OutputChannels</b>. The client can then send a second property request with enough storage allocated to contain the capabilities of all the channels.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537291">KSPROPERTY_AUDIO_MIX_LEVEL_CAPS</a>



<a href="..\ksmedia\ns-ksmedia-ksaudio_mix_caps.md">KSAUDIO_MIX_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537292">KSPROPERTY_AUDIO_MIX_LEVEL_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537198">KSNODETYPE_SUPERMIX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_MIXCAP_TABLE structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

