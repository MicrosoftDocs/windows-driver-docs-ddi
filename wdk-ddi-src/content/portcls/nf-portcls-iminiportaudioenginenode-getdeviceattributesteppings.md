---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceAttributeSteppings
title: IMiniportAudioEngineNode::GetDeviceAttributeSteppings (portcls.h)
description: Gets the allowed stepping value for the audio device attribute.
old-location: audio\iminiportaudioenginenode_getdeviceattributesteppings.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioEngineNode::GetDeviceAttributeSteppings"]
ms.keywords: GetDeviceAttributeSteppings, GetDeviceAttributeSteppings method [Audio Devices], GetDeviceAttributeSteppings method [Audio Devices],IMiniportAudioEngineNode interface, IMiniportAudioEngineNode interface [Audio Devices],GetDeviceAttributeSteppings method, IMiniportAudioEngineNode.GetDeviceAttributeSteppings, IMiniportAudioEngineNode::GetDeviceAttributeSteppings, audio.iminiportaudioenginenode_getdeviceattributesteppings, portcls/IMiniportAudioEngineNode::GetDeviceAttributeSteppings
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
 - IMiniportAudioEngineNode::GetDeviceAttributeSteppings
 - portcls/IMiniportAudioEngineNode::GetDeviceAttributeSteppings
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioEngineNode.GetDeviceAttributeSteppings
---

# IMiniportAudioEngineNode::GetDeviceAttributeSteppings


## -description

Gets the allowed stepping value for the audio device attribute.

## -parameters

### -param ulNodeId 

[in]
The ID for the node that represents the audio device.

### -param targetType 

[in]
An  <a href="/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a> enumerated value that specifies the type of target node. For example, a Volume or a Mute node.

### -param pKsPropStepLong 

[out]
A structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_stepping_long">KSPROPERTY_STEPPING_LONG</a> that contains information about the allowed stepping value for the device attribute.

### -param ui32DataSize 

[in]
The allowed stepping value.

## -returns

<b>GetDeviceAttributeSteppings</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportaudioenginenode">IMiniportAudioEngineNode</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_stepping_long">KSPROPERTY_STEPPING_LONG</a>



<a href="/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a>
