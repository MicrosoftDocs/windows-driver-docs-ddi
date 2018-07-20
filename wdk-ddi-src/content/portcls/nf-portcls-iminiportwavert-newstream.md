---
UID: NF:portcls.IMiniportWaveRT.NewStream
title: IMiniportWaveRT::NewStream
author: windows-driver-content
description: The NewStream method creates a new instance of a WaveRT stream object.
old-location: audio\iminiportwavert_newstream.htm
tech.root: audio
ms.assetid: efd2eea8-2b05-49a2-b136-a3e1e3e739c5
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IMiniportWaveRT interface [Audio Devices],NewStream method, IMiniportWaveRT.NewStream, IMiniportWaveRT::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportWaveRT interface, audio.iminiportwavert_newstream, audmp-routines_f6e65bf7-d19d-42fc-a0f0-2d2c83e88250.xml, portcls/IMiniportWaveRT::NewStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRT.NewStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveRT::NewStream


## -description


The <code>NewStream</code> method creates a new instance of a WaveRT stream object.


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable, into which the <code>NewStream</code> method writes a pointer to the <b>IMiniportWaveRTStream</b> interface of the new stream object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param PortStream [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>.


### -param Pin [in]

Specifies a pin ID that identifies the pin to be opened. If the filter descriptor of the WaveRT miniport driver specifies a total of <i>n</i> pin factories on the filter, valid values for the <i>Pin</i> parameter are in the range 0 to <i>n</i>-1. For more information about filter descriptors, see the <a href="https://msdn.microsoft.com/e836f941-274f-4e27-8069-753ef9ef2a06">Filter Factories</a> topic. 


### -param Capture [in]

Specifies a Boolean value that indicates whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for a capture (input) stream, and <b>FALSE</b> for a playback (output) stream.


### -param DataFormat [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure that specifies the data format of the new stream. For more information, see the following Remarks section.


## -returns



<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.




## -remarks



The <code>NewStream</code> method sets the initial state of the stream to <a href="https://msdn.microsoft.com/c71fd395-28aa-4421-9443-b5b0a1f3ac7e">KSSTATE_STOP</a> and its initial position to 0. For more information, see related methods <a href="https://msdn.microsoft.com/library/windows/hardware/ff536756">IMiniportWaveRTStream::SetState</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536749">IMiniportWaveRTStream::GetPosition</a>.

The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the KSDATAFORMAT structure:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537095">KSDATAFORMAT_WAVEFORMATEX</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537094">KSDATAFORMAT_DSOUND</a>


</li>
</ul>
The <i>Stream</i> and <i>PortStream</i> parameters follow the reference-counting conventions for COM objects.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536737">IMiniportWaveRT</a>



IMiniportWaveRTStream



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536749">IMiniportWaveRTStream::GetPosition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536756">IMiniportWaveRTStream::SetState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536922">IPortWaveRTStream</a>
 

 

