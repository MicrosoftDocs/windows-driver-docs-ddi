---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceFormat
title: IMiniportAudioEngineNode::GetDeviceFormat (portcls.h)
description: Gets the audio data format for an audio device.
old-location: audio\iminiportaudioenginenode_getdeviceformat.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetDeviceFormat"]
ms.keywords: GetDeviceFormat, GetDeviceFormat method [Audio Devices], GetDeviceFormat method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceFormat method, IMiniportAudioEngineNode.GetDeviceFormat, IMiniportAudioEngineNode::GetDeviceFormat, audio.iminiportaudioenginenode_getdeviceformat, portcls/IMiniportAudioEngineNode::GetDeviceFormat
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
 - IMiniportAudioEngineNode::GetDeviceFormat
 - portcls/IMiniportAudioEngineNode::GetDeviceFormat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode::GetDeviceFormat
---

# IMiniportAudioEngineNode::GetDeviceFormat


## -description

Gets the audio data format for an audio device.

## -parameters

### -param ulNodeId 

[in]
The ID of the device node.

### -param pFormat 

[out]
A structure of type  <a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a> that represents the audio data format for the device.

### -param ulBufferSize 

[in]
The audio data buffer size.

## -returns

<b>GetDeviceFormat</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>

