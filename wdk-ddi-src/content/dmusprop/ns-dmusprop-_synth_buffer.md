---
UID: NS:dmusprop._SYNTH_BUFFER
title: _SYNTH_BUFFER (dmusprop.h)
description: The SYNTH_BUFFER structure specifies DLS data that is being downloaded to a synthesizer.
old-location: audio\synth_buffer.htm
tech.root: audio
ms.assetid: 51b16308-47a8-42e0-9393-fd93045e4e47
ms.date: 05/08/2018
ms.keywords: "*PSYNTH_BUFFER, PSYNTH_BUFFER, PSYNTH_BUFFER structure pointer [Audio Devices], SYNTH_BUFFER, SYNTH_BUFFER structure [Audio Devices], _SYNTH_BUFFER, aud-prop_297e165a-cb0d-4ea1-b69c-b65bcb4ee69a.xml, audio.synth_buffer, dmusprop/PSYNTH_BUFFER, dmusprop/SYNTH_BUFFER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dmusprop.h
api_name:
- SYNTH_BUFFER
product:
- Windows
targetos: Windows
req.typenames: SYNTH_BUFFER, *PSYNTH_BUFFER
---

# _SYNTH_BUFFER structure


## -description


The SYNTH_BUFFER structure specifies DLS data that is being downloaded to a synthesizer.


## -struct-fields




### -field BufferSize

Specifies the size in bytes of the buffer that <b>BufferAddress</b> points to.


### -field BufferAddress

Pointer to a user-mode address that needs to be converted for kernel use.


## -remarks



A <a href="https://docs.microsoft.com/previous-versions/ff537396(v=vs.85)">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a> set-property request uses the SYNTH_BUFFER structure for its property value.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff537396(v=vs.85)">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a>
 

 

