---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings
title: IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings (portcls.h)
description: Gets the allowed stepping value for the audio stream attribute.
old-location: audio\iminiportstreamaudioenginenode_getstreamattributesteppings.htm
tech.root: audio
ms.assetid: 2EC0C859-5479-4A55-9180-DB9938400DF7
ms.date: 05/08/2018
keywords: ["IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings"]
ms.keywords: GetStreamAttributeSteppings, GetStreamAttributeSteppings method [Audio Devices], GetStreamAttributeSteppings method [Audio Devices],IMiniportStreamAudioEngineNode interface, IMiniportStreamAudioEngineNode interface [Audio Devices],GetStreamAttributeSteppings method, IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings, IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings, audio.iminiportstreamaudioenginenode_getstreamattributesteppings, portcls/IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings
f1_keywords:
 - "portcls/IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings"
 - "IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings"
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
- IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings
targetos: Windows
req.typenames: 
---

# IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings


## -description


Gets the allowed stepping value for the audio stream attribute.


## -parameters




### -param targetType [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a> enumerated value that specifies the  target node type.


### -param pKsPropStepLong [out]

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_stepping_long">KSPROPERTY_STEPPING_LONG</a> that contains information about the allowed stepping value for the audio stream attribute.


### -param ui32DataSize [in]

The allowed stepping value.


## -returns



<b>GetStreamAttributeSteppings</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportstreamaudioenginenode">IMiniportStreamAudioEngineNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_stepping_long">KSPROPERTY_STEPPING_LONG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ne-portcls-echanneltargettype">eChannelTargetType</a>
 

 

