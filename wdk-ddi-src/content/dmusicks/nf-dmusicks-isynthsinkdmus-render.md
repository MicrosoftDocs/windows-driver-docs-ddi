---
UID: NF:dmusicks.ISynthSinkDMus.Render
title: ISynthSinkDMus::Render method
author: windows-driver-content
description: The Render method renders wave data into a destination sink.
old-location: audio\isynthsinkdmus_render.htm
old-project: audio
ms.assetid: 731abdaf-f84b-4d4b-a6e0-ee11899fba27
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ISynthSinkDMus, ISynthSinkDMus interface [Audio Devices], Render method, ISynthSinkDMus::Render, Render method [Audio Devices], Render method [Audio Devices], ISynthSinkDMus interface, Render,ISynthSinkDMus.Render, audio.isynthsinkdmus_render, audmp-routines_ada0270e-6234-4508-a323-f4bdaee295ce.xml, dmusicks/ISynthSinkDMus::Render
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dmusicks.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	ISynthSinkDMus.Render
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# ISynthSinkDMus::Render method


## -description


The <code>Render</code> method renders wave data into a destination sink.


## -syntax


````
void Render(
  [in] PBYTE    pBuffer,
  [in] DWORD    dwLength,
  [in] LONGLONG llPosition
);
````


## -parameters




### -param pBuffer [in]

Pointer to the buffer that the synth sink wants data written to


### -param dwLength [in]

Specifies the length (in bytes) of the data to be rendered.


### -param llPosition [in]

Specifies the position (in bytes) in the PCM buffer at which to begin rendering. Rendering continues from this position for the number of bytes specified in <i>dwLength</i>.


## -returns



None




## -remarks



The port driver's synth-sink object calls this method when the miniport driver needs to render more wave data into the destination buffer.



