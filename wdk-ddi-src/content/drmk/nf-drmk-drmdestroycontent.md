---
UID: NF:drmk.DrmDestroyContent
title: DrmDestroyContent function
author: windows-driver-content
description: The DrmDestroyContent function deletes a DRM content ID that was created by DrmCreateContentMixed.
old-location: audio\drmdestroycontent.htm
old-project: audio
ms.assetid: 197f74f8-050e-4b0b-a95d-f640c565c17e
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: DrmDestroyContent, DrmDestroyContent function [Audio Devices], aud-prop2_cfaec95c-a7e5-4488-a56d-323ebc577d90.xml, audio.drmdestroycontent, drmk/DrmDestroyContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Drmk.lib
-	Drmk.dll
api_name:
-	DrmDestroyContent
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# DrmDestroyContent function


## -description


The <code>DrmDestroyContent</code> function deletes a DRM content ID that was created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>.


## -parameters




### -param ContentId [in]

Specifies a nonzero DRM content ID assigned to a KS audio stream by <b>DrmCreateContentMixed</b>. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


## -returns



<b>DrmCreateContentMixed</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



A KS audio filter can only use <code>DrmDestroyContent</code> to delete a DRM content ID that it obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>. Note that a KS audio filter must not use <code>DrmDestroyContent</code> to delete a DRM content ID set by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a> or by an IOCTL_KS_PROPERTY request that sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> property. Only the KS audio filter that created the content ID should delete it.

<code>DrmDestroyContent</code> performs the same function as <a href="https://msdn.microsoft.com/library/windows/hardware/ff537690">PcDestroyContent</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536583">IDrmPort::DestroyContent</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536583">IDrmPort::DestroyContent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537690">PcDestroyContent</a>
 

 

