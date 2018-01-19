---
UID: NF:dmusicks.ISynthSinkDMus.Render
title: ISynthSinkDMus::Render method
author: windows-driver-content
description: The Render method renders wave data into a destination sink.
old-location: audio\isynthsinkdmus_render.htm
old-project: audio
ms.assetid: 731abdaf-f84b-4d4b-a6e0-ee11899fba27
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISynthSinkDMus, ISynthSinkDMus::Render, Render
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISynthSinkDMus.Render
req.alt-loc: dmusicks.h
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
req.typenames: DMUS_STREAM_TYPE
---

# ISynthSinkDMus::Render method



## -description
The <code>Render</code> method renders wave data into a destination sink.



## -syntax

````
void Render(
  [in] PBYTE    pbBuffer,
  [in] DWORD    dwLength,
  [in] LONGLONG llPosition
);
````


## -parameters

### -param pbBuffer [in]

Pointer to the buffer that the synth sink wants data written to


### -param dwLength [in]

Specifies the length (in bytes) of the data to be rendered.


### -param llPosition [in]

Specifies the position (in bytes) in the PCM buffer at which to begin rendering. Rendering continues from this position for the number of bytes specified in <i>dwLength</i>.


## -returns
None


## -remarks
The port driver's synth-sink object calls this method when the miniport driver needs to render more wave data into the destination buffer.</p>