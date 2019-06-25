---
UID: NF:portcls.IMiniportAudioEngineNode.GetSupportedDeviceFormats
title: IMiniportAudioEngineNode::GetSupportedDeviceFormats (portcls.h)
description: Gets the supported audio data formats for the audio device.
old-location: audio\iminiportaudioenginenode_getsupporteddeviceformats.htm
tech.root: audio
ms.assetid: 2B27E92C-8781-4499-A1E0-7C1BBFFAA2DF
ms.date: 05/08/2018
ms.keywords: GetSupportedDeviceFormats, GetSupportedDeviceFormats method [Audio Devices], GetSupportedDeviceFormats method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetSupportedDeviceFormats method, IMiniportAudioEngineNode.GetSupportedDeviceFormats, IMiniportAudioEngineNode::GetSupportedDeviceFormats, audio.iminiportaudioenginenode_getsupporteddeviceformats, portcls/IMiniportAudioEngineNode::GetSupportedDeviceFormats
ms.topic: method
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.h
api_name:
- IMiniportAudioEngineNode.GetSupportedDeviceFormats
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportAudioEngineNode::GetSupportedDeviceFormats


## -description


Gets the supported audio data formats for the audio device.


## -parameters




### -param ulNodeId [in]

The ID of the node that represents the audio device.


### -param pFormats [out]

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> that points to the array of audio data formats supported by the audio device.


### -param ulBufferSize [in]

The buffer size for the audio data format information.


## -returns



<b>GetSupportedDeviceFormats</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a>
 

 

