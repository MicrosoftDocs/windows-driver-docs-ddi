---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceAttributeSteppings
title: IMiniportAudioEngineNode::GetDeviceAttributeSteppings method
author: windows-driver-content
description: Gets the allowed stepping value for the audio device attribute.
old-location: audio\iminiportaudioenginenode_getdeviceattributesteppings.htm
old-project: audio
ms.assetid: 7AF6C9AF-8955-4F09-A42C-097B4AD1CD3A
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetDeviceAttributeSteppings method [Audio Devices], GetDeviceAttributeSteppings method [Audio Devices], IMiniportAudioEngineNode interface, GetDeviceAttributeSteppings,IMiniportAudioEngineNode.GetDeviceAttributeSteppings, IMiniportAudioEngineNode, IMiniportAudioEngineNode interface [Audio Devices], GetDeviceAttributeSteppings method, IMiniportAudioEngineNode::GetDeviceAttributeSteppings, audio.iminiportaudioenginenode_getdeviceattributesteppings, portcls/IMiniportAudioEngineNode::GetDeviceAttributeSteppings
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportAudioEngineNode.GetDeviceAttributeSteppings
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetDeviceAttributeSteppings method


## -description


Gets the allowed stepping value for the audio device attribute.


## -parameters




### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param targetType [in]

An  <a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a> enumerated value that specifies the type of target node. For example, a Volume or a Mute node.


### -param pKsPropStepLong [out]

A structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a> that contains information about the allowed stepping value for the device attribute.


### -param ui32DataSize [in]

The allowed stepping value.


## -returns



<b>GetDeviceAttributeSteppings</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302040">IMiniportAudioEngineNode</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302034">eChannelTargetType</a>
 

 

