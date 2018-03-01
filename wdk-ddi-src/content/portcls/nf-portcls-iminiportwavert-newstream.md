---
UID: NF:portcls.IMiniportWaveRT.NewStream
title: IMiniportWaveRT::NewStream method
author: windows-driver-content
description: The NewStream method creates a new instance of a WaveRT stream object.
old-location: audio\iminiportwavert_newstream.htm
old-project: audio
ms.assetid: efd2eea8-2b05-49a2-b136-a3e1e3e739c5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMiniportWaveRT, IMiniportWaveRT interface [Audio Devices], NewStream method, IMiniportWaveRT::NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices], IMiniportWaveRT interface, NewStream,IMiniportWaveRT.NewStream, audio.iminiportwavert_newstream, audmp-routines_f6e65bf7-d19d-42fc-a0f0-2d2c83e88250.xml, portcls/IMiniportWaveRT::NewStream
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
req.lib: portcls.h
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
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRT::NewStream method


## -description


The <code>NewStream</code> method creates a new instance of a WaveRT stream object.


## -syntax


````
NTSTATUS NewStream(
  [out] PMINIPORTWAVERTSTREAM *Stream,
  [in]  PPORTWAVERTSTREAM     PortStream,
  [in]  ULONG                 Pin,
  [in]  BOOLEAN               Capture,
  [in]  PKSDATAFORMAT         DataFormat
);
````


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable, into which the <code>NewStream</code> method writes a pointer to the <b>IMiniportWaveRTStream</b> interface of the new stream object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param PortStream [in]

Pointer to the <a href="..\portcls\nn-portcls-iportwavertstream.md">IPortWaveRTStream</a>.


### -param Pin [in]

Specifies a pin ID that identifies the pin to be opened. If the filter descriptor of the WaveRT miniport driver specifies a total of <i>n</i> pin factories on the filter, valid values for the <i>Pin</i> parameter are in the range 0 to <i>n</i>-1. For more information about filter descriptors, see the <a href="https://msdn.microsoft.com/e836f941-274f-4e27-8069-753ef9ef2a06">Filter Factories</a> topic. 


### -param Capture [in]

Specifies a Boolean value that indicates whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for a capture (input) stream, and <b>FALSE</b> for a playback (output) stream.


### -param DataFormat [in]

Pointer to a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure that specifies the data format of the new stream. For more information, see the following Remarks section.


## -returns



<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.




## -remarks



The <code>NewStream</code> method sets the initial state of the stream to <a href="https://msdn.microsoft.com/c71fd395-28aa-4421-9443-b5b0a1f3ac7e">KSSTATE_STOP</a> and its initial position to 0. For more information, see related methods <a href="https://msdn.microsoft.com/library/windows/hardware/ff536756">IMiniportWaveRTStream::SetState</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536749">IMiniportWaveRTStream::GetPosition</a>.

The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the KSDATAFORMAT structure:

<ul>
<li>

<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>


</li>
<li>

<a href="..\ksmedia\ns-ksmedia-ksdataformat_dsound.md">KSDATAFORMAT_DSOUND</a>


</li>
</ul>
The <i>Stream</i> and <i>PortStream</i> parameters follow the reference-counting conventions for COM objects.




## -see-also

<a href="..\portcls\nn-portcls-iminiportwavert.md">IMiniportWaveRT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536749">IMiniportWaveRTStream::GetPosition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536756">IMiniportWaveRTStream::SetState</a>



IMiniportWaveRTStream



<a href="..\portcls\nn-portcls-iminiportwavertstream.md">IPortWaveRTStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRT::NewStream method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

