---
UID: NS:dmusprop._SYNTH_STATS
title: _SYNTH_STATS (dmusprop.h)
description: The SYNTH_STATS structure specifies synthesizer performance statistics such as the number of voices playing, CPU usage, number of notes lost, amount of free memory, and peak volume level.
old-location: audio\synth_stats.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["SYNTH_STATS structure"]
ms.keywords: "*PSYNTH_STATS, PSYNTH_STATS, PSYNTH_STATS structure pointer [Audio Devices], SYNTH_STATS, SYNTH_STATS structure [Audio Devices], _SYNTH_STATS, aud-prop_04ed015d-56c6-4275-8025-66e67ee6ce87.xml, audio.synth_stats, dmusprop/PSYNTH_STATS, dmusprop/SYNTH_STATS"
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
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
f1_keywords:
 - _SYNTH_STATS
 - dmusprop/_SYNTH_STATS
 - PSYNTH_STATS
 - dmusprop/PSYNTH_STATS
 - SYNTH_STATS
 - dmusprop/SYNTH_STATS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dmusprop.h
api_name:
 - _SYNTH_STATS
 - PSYNTH_STATS
 - SYNTH_STATS
---

# _SYNTH_STATS structure


## -description

The SYNTH_STATS structure specifies synthesizer performance statistics such as the number of voices playing, CPU usage, number of notes lost, amount of free memory, and peak volume level.

## -struct-fields

### -field ValidStats

Specifies which members of the SYNTH_STATS structure contain valid data. This member is a bitfield whose value is either zero or a bitwise OR of one or more of the following flag bits:





#### SYNTH_STATS_VOICES

The <b>Voices</b> field contains valid data.



#### SYNTH_STATS_TOTAL_CPU

The <b>TotalCPU</b> field contains valid data.



#### SYNTH_STATS_CPU_PER_VOICE

The <b>CPUPerVoice</b> field contains valid data.



#### SYNTH_STATS_LOST_NOTES

The <b>LostNotes </b>field contains valid data.



#### SYNTH_STATS_PEAK_VOLUME

The <b>PeakVolume </b>field contains valid data.



#### SYNTH_STATS_FREE_MEMORY

The <b>FreeMemory</b> field contains valid data.

### -field Voices

Specifies the average number of voices playing.

### -field TotalCPU

Specifies the total CPU usage (all voices), which is expressed as a percentage (a fraction multiplied by 100).

### -field CPUPerVoice

Specifies the CPU usage per voice, which is expressed as a percentage (a fraction multiplied by 100).

### -field LostNotes

Specifies the number of notes lost. Notes can be dropped if the number of simultaneous voices exceeds the maximum specified by the <a href="/previous-versions/ff537405(v=vs.85)">KSPROPERTY_SYNTH_PORTPARAMETERS</a> property. For additional information, see <a href="/windows-hardware/drivers/audio/voice-allocation">Voice Allocation</a>.

### -field FreeMemory

Specifies the amount of free memory in bytes. This is the storage that remains available for downloading additional DLS data resources.

### -field PeakVolume

Specifies the peak volume level expressed as decibels multiplied by 100.

## -remarks

The <a href="/previous-versions/ff537406(v=vs.85)">KSPROPERTY_SYNTH_RUNNINGSTATS</a> property uses the SYNTH_STATS structure to query a DirectMusic miniport driver for statistics about a synthesizer.

The SYNTH_STATS structure is similar to the DMUS_SYNTHSTATS structure, which is described in the Microsoft Windows SDK documentation.

## -see-also

<a href="/previous-versions/ff537405(v=vs.85)">KSPROPERTY_SYNTH_PORTPARAMETERS</a>



<a href="/previous-versions/ff537406(v=vs.85)">KSPROPERTY_SYNTH_RUNNINGSTATS</a>

