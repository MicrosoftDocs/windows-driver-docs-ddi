---
UID: NF:portcls.IMiniportAudioEngineNode.SetDeviceFormat
title: IMiniportAudioEngineNode::SetDeviceFormat (portcls.h)
description: Sets the audio data format for an audio device.
old-location: audio\iminiportaudioenginenode_setdeviceformat.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::SetDeviceFormat"]
ms.keywords: IMiniportAudioEngineNode interface [Audio Devices],SetDeviceFormat method, IMiniportAudioEngineNode.SetDeviceFormat, IMiniportAudioEngineNode::SetDeviceFormat, SetDeviceFormat, SetDeviceFormat method [Audio Devices], SetDeviceFormat method [Audio Devices],IMiniportAudioEngineNode interface, audio.iminiportaudioenginenode_setdeviceformat, portcls/IMiniportAudioEngineNode::SetDeviceFormat
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: 
f1_keywords:
 - IMiniportAudioEngineNode::SetDeviceFormat
 - portcls/IMiniportAudioEngineNode::SetDeviceFormat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode.SetDeviceFormat
---

# IMiniportAudioEngineNode::SetDeviceFormat


## -description

Sets the audio data format for an audio device.

## -parameters

### -param ulNodeId 

[in]
The ID of the node that represents the device.

### -param pFormat 

[in]
A structure of type <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format to be set for the device.

### -param ulBufferSize 

[in]
The audio data buffer size.

## -returns

<b>SetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>
