---
UID: NF:portcls.IMiniportAudioSignalProcessing.GetModes
title: IMiniportAudioSignalProcessing::GetModes method
author: windows-driver-content
description: The GetModes method, Gets the audio signal processing modes supported by an audio pin.
old-location: audio\iminiportaudiosignalprocessing_getmodes.htm
old-project: audio
ms.assetid: 7175453E-DF6D-45F0-B666-CF4FCF1F880C
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetModes method [Audio Devices], GetModes method [Audio Devices], IMiniportAudioSignalProcessing interface, GetModes,IMiniportAudioSignalProcessing.GetModes, IMiniportAudioSignalProcessing, IMiniportAudioSignalProcessing interface [Audio Devices], GetModes method, IMiniportAudioSignalProcessing::GetModes, audio.iminiportaudiosignalprocessing_getmodes, portcls/IMiniportAudioSignalProcessing::GetModes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioSignalProcessing.GetModes
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioSignalProcessing::GetModes method


## -description


The GetModes method, Gets the audio signal processing modes supported by an audio pin.


## -parameters




### -param Pin [in]

The index of the audio pin.


### -param SignalProcessingModes [out, optional]

This parameter is optional. It returns an array of GUIDs that identify the  signal processing modes supported by the  <i>Pin</i> parameter.


### -param NumSignalProcessingModes [in, out]

When used as an input, it specifies the number of elements that can be written to the buffer that is specified in <i>SignalProcessingModes</i>. When used as an output, it returns the number of elements that were written to the buffer.


## -returns



<b>GetModes</b> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



If <i>SignalProcessingModes</i> is NULL, then <b>GetModes</b> writes the number of supported modes to <i>NumSignalProcessingModes</i> and returns STATUS_SUCCESS. This allows callers to query the number of supported modes in order to allocate buffers.

If <i>SignalProcessingModes</i> is not NULL, then <b>GetModes</b> verifies that <i>NumSignalProcessingModes</i> is greater than or equal to the number of supported modes. If it is, then the method writes the supported modes to the <i>SignalProcessingModes</i> buffer, writes the actual number of supported modes to <i>NumSignalProcessingModes</i>, and returns STATUS_SUCCESS.

The following table presents and explains  the error messages than can be returned by <b>GetModes</b>.

<table>
<tr>
<th>Error code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td> The buffer that was set aside for <i>NumSignalProcessingModes</i> is too small.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>The value of the <i>Pin</i> parameter indicates a Pin ID that is &gt;= the number of pin factories on the filter. The pin index is zero-based, so for n pin factories on a filter, the highest index value should be n-1.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>A Pin ID was specified for a pin which does not support signal processing modes. For example,  if the Pin ID refers to an audio loopback pin  or a bridge pin, then <b>GetModes</b> will return this error code.</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn457659">IMiniportAudioSignalProcessing</a>
 

 

