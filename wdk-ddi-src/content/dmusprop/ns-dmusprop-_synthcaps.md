---
UID: NS:dmusprop._SYNTHCAPS
title: "_SYNTHCAPS"
author: windows-driver-content
description: The SYNTHCAPS structure specifies the capabilities of a synthesizer.
old-location: audio\synthcaps.htm
old-project: audio
ms.assetid: d9d7327f-a413-4828-b204-e08198d0fe9e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PSYNTHCAPS, PSYNTHCAPS, PSYNTHCAPS structure pointer [Audio Devices], SYNTHCAPS, SYNTHCAPS structure [Audio Devices], _SYNTHCAPS, aud-prop_609e484a-6bcb-4ea2-9ca5-fa640c4d9ba8.xml, audio.synthcaps, dmusprop/PSYNTHCAPS, dmusprop/SYNTHCAPS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: Dmusprop.h
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
-	dmusprop.h
api_name:
-	SYNTHCAPS
product:
- Windows
targetos: Windows
req.typenames: SYNTHCAPS, *PSYNTHCAPS
---

# _SYNTHCAPS structure


## -description


The SYNTHCAPS structure specifies the capabilities of a synthesizer.


## -struct-fields




### -field Guid

Specifies the class ID for the synthesizer's miniport driver interface.


### -field Flags

Specifies the general capabilities of the driver. This member is a bitfield whose value is either zero or the bitwise OR of one or more of the following flag bits:





#### SYNTH_PC_DLS

The driver supports downloadable sample collections (DLS Level 1).



#### SYNTH_PC_EXTERNAL

The synth represents a connection to external hardware.



#### SYNTH_PC_SOFTWARESYNTH

The driver implements a software synthesizer.



#### SYNTH_PC_MEMORYSIZEFIXED

The memory size given in the <b>MemorySize</b> member is valid and represents the maximum amount of sample memory in bytes. This flag is typically set when the sample memory is not system memory.



#### SYNTH_PC_GMINHARDWARE

The synth supports the General MIDI sound set in hardware.



#### SYNTH_PC_GSINHARDWARE

The synth supports the Roland GS sound set in hardware.



#### SYNTH_PC_REVERB

The synth supports reverb.



#### SYNTH_PC_DLS2

The driver supports downloadable sample collections (DLS Level 2).



#### SYNTH_PC_SYSTEMMEMORY

The synth can use system memory.


### -field MemorySize

Specifies the amount of sample memory on the device (in bytes). This field should contain the value SYNTH_PC_SYSTEMMEMORY if the device uses system memory for sample memory with no limitation on the amount of memory allocated.


### -field MaxChannelGroups

Specifies the maximum number of channel groups this driver supports. Each channel group represents a set of 16 MIDI channels and has associated with it all the state that a MIDI hardware device would keep, which includes DLS, GM, GS, XG, or other mode information. DLS downloads, however, are per-driver and can be used by any of the channel groups. This prevents wasting memory by downloading several copies of the same DLS sample, one per channel group.


### -field MaxVoices

Specifies the maximum number of voices that the rendering device supports. If the property handler is unable to provide a valid number for this member, it should set the member to (ULONG)-1.


### -field MaxAudioChannels

Specifies the maximum number of audio channels that the rendering device supports. If the property handler is unable to provide a valid number for this member, it should set the member to (ULONG)-1.


### -field EffectFlags

Specifies the effects that the rendering device is capable of producing. This member is a bitfield whose value is either zero or the bitwise OR of the following flag bits:





#### SYNTH_EFFECT_REVERB

Rendering device can produce reverb effect.



#### SYNTH_EFFECT_CHORUS

Rendering device can produce chorus effect.



#### SYNTH_EFFECT_DELAY

Rendering device can produce delay effect.

If the device supports none of these capabilities, set this member to SYNTH_EFFECT_NONE (zero).


### -field Description

Contains a text description of the device. This member is a WCHAR array containing a null-terminated string (for example, "Microsoft MPU-401").


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537389">KSPROPERTY_SYNTH_CAPS</a> get-property request uses the SYNTHCAPS structure to retrieve the capabilities of a synthesizer device from a DMus miniport driver.

SYNTH_CAPS is similar to the DMUS_PORTCAPS structure, which is described in the Microsoft Windows SDK documentation.

In the DMusUART sample driver in the Windows Driver Kit (WDK), the KSPROPERTY_SYNTH_CAPS property handler sets the members of the SYNTHCAPS structure to the following values:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  SYNTHCAPS *caps = (SYNTHCAPS*)pRequest-&gt;Value;
  ...
  caps-&gt;Flags              = SYNTH_PC_EXTERNAL;
  caps-&gt;MemorySize         = 0;         
  caps-&gt;MaxChannelGroups   = 1;
  caps-&gt;MaxVoices          = 0xFFFFFFFF;  // (ULONG)-1
  caps-&gt;MaxAudioChannels   = 0xFFFFFFFF;  // (ULONG)-1
  caps-&gt;EffectFlags        = 0;</pre>
</td>
</tr>
</table></span></div>
In this example, the 0xFFFFFFFF values indicate that the handler has no way of knowing the actual <b>MaxVoices</b> and <b>MaxAudioChannels</b> limits because they are completely dependent on whatever external synthesizer happens to be connected to the UART. Elsewhere in the code, but not shown in the preceding example, the DMusUART property handler sets the <b>Guid</b> member of the SYNTHCAPS structure to either <b>CLSID_MiniportDriverDMusUART</b> or <b>CLSID_MiniportDriverDMusUARTCapture</b>. The one the <b>Guid</b> member is it is set to depends on whether the target node (of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537203">KSNODETYPE_SYNTHESIZER</a>) for the property request lies on a data path that handles rendering data or capture data. Both class IDs are defined in header file Dmusicks.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537203">KSNODETYPE_SYNTHESIZER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537389">KSPROPERTY_SYNTH_CAPS</a>
 

 

