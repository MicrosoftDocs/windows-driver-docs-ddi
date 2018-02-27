---
UID: NF:portcls.IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings
title: IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings method
author: windows-driver-content
description: Gets the allowed stepping value for the audio stream attribute.
old-location: audio\iminiportstreamaudioenginenode_getstreamattributesteppings.htm
old-project: audio
ms.assetid: 2EC0C859-5479-4A55-9180-DB9938400DF7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: GetStreamAttributeSteppings method [Audio Devices], GetStreamAttributeSteppings method [Audio Devices], IMiniportStreamAudioEngineNode interface, GetStreamAttributeSteppings,IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings, IMiniportStreamAudioEngineNode, IMiniportStreamAudioEngineNode interface [Audio Devices], GetStreamAttributeSteppings method, IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings, audio.iminiportstreamaudioenginenode_getstreamattributesteppings, portcls/IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.h
apiname:
-	IMiniportStreamAudioEngineNode.GetStreamAttributeSteppings
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings method


## -description


Gets the allowed stepping value for the audio stream attribute.


## -syntax


````
NTSTATUS GetStreamAttributeSteppings(
  [in]  eChannelTargetType        targetType,
  [out] PKSPROPERTY_STEPPING_LONG pKsPropStepLong,
  [in]  UINT32                    ui32DataSize
);
````


## -parameters




### -param targetType [in]

An <a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a> enumerated value that specifies the  target node type.


### -param pKsPropStepLong [out]

A structure of type <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a> that contains information about the allowed stepping value for the audio stream attribute.


### -param ui32DataSize [in]

The allowed stepping value.


## -returns



<b>GetStreamAttributeSteppings</b> returns S_OK, if the call was successful. Otherwise, the method returns an appropriate error 

code.




## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565631(v=vs.85).aspx">KSPROPERTY_STEPPING_LONG</a>



<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode.md">IMiniportStreamAudioEngineNode</a>



<a href="..\portcls\ne-portcls-echanneltargettype.md">eChannelTargetType</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportStreamAudioEngineNode::GetStreamAttributeSteppings method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

