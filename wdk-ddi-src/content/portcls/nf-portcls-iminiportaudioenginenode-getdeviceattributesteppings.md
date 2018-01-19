---
UID: NF:portcls.IMiniportAudioEngineNode.GetDeviceAttributeSteppings
title: IMiniportAudioEngineNode::GetDeviceAttributeSteppings method
author: windows-driver-content
description: Gets the allowed stepping value for the audio device attribute.
old-location: audio\iminiportaudioenginenode_getdeviceattributesteppings.htm
old-project: audio
ms.assetid: 7AF6C9AF-8955-4F09-A42C-097B4AD1CD3A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportAudioEngineNode, IMiniportAudioEngineNode::GetDeviceAttributeSteppings, GetDeviceAttributeSteppings
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
req.alt-api: IMiniportAudioEngineNode.GetDeviceAttributeSteppings
req.alt-loc: Portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportAudioEngineNode::GetDeviceAttributeSteppings method



## -description
Gets the allowed stepping value for the audio device attribute.



## -syntax

````
NTSTATUS GetDeviceAttributeSteppings(
  [in]  ULONG                     ulNodeId,
  [in]  eChannelTargetType        targetType,
  [out] PKSPROPERTY_STEPPING_LONG pKsPropStepLong,
  [in]  UINT32                    ui32DataSize
);
````


## -parameters

### -param ulNodeId [in]

The ID for the node that represents the audio device.


### -param targetType [in]

An  <a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a> enumerated value that specifies the type of target node. For example, a Volume or a Mute node.


### -param pKsPropStepLong [out]

A structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a> that contains information about the allowed stepping value for the device attribute.


### -param ui32DataSize [in]

The allowed stepping value.


## -returns
<b>GetDeviceAttributeSteppings</b> returns S_OK, if the call was successful. Otherwise, the method 

returns an appropriate error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iminiportaudioenginenode.md">IMiniportAudioEngineNode</a>
</dt>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportAudioEngineNode::GetDeviceAttributeSteppings method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

