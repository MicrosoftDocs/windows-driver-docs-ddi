---
UID: NF:drmk.IDrmAudioStream.SetContentId
title: IDrmAudioStream::SetContentId method
author: windows-driver-content
description: The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.
old-location: audio\idrmaudiostream_setcontentid.htm
old-project: audio
ms.assetid: 0e9d13e8-c351-4730-8f00-6c149f824af0
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IDrmAudioStream, IDrmAudioStream interface [Audio Devices], SetContentId method, IDrmAudioStream::SetContentId, SetContentId method [Audio Devices], SetContentId method [Audio Devices], IDrmAudioStream interface, SetContentId,IDrmAudioStream.SetContentId, audio.idrmaudiostream_setcontentid, audmp-routines_66106418-566d-4203-a6d6-faae74a6db13.xml, drmk/IDrmAudioStream::SetContentId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	drmk.h
api_name:
-	IDrmAudioStream.SetContentId
product:
- Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# IDrmAudioStream::SetContentId method


## -description


The <code>SetContentId</code> method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter is an identifier that the DRM system generates at run time to identify DRM-protected content in this stream.


### -param DrmRights [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a> structure specifying the rights granted by the content provider to the user for playing and copying DRM-protected content in this stream.


## -returns



<code>SetContentId</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. If the filter cannot enforce the specified content rights, the method returns STATUS_NOT_IMPLEMENTED.




## -remarks



The DRM system can call the <code>SetContentId</code> method at any time during the lifetime of a KS audio stream.

A KS audio filter completes the execution of a call to the <code>SetContentId</code> method synchronously. If the function returns STATUS_SUCCESS, this indicates that all the downstream KS audio nodes (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536219">Audio Topology Nodes</a>) of a KS audio stream have also been successfully configured with the specified DRM content ID and DRM content rights. (The term <i>downstream node</i> refers to either a direct or an indirect sink for an audio stream.)

If the KS audio filter cannot enforce the specified DRM content rights, the <code>SetContentId</code> method returns the error code STATUS_NOT_IMPLEMENTED. In this case, the KS audio stream's previously set DRM content ID and DRM content rights remain set on the stream.

For more information about using this method, see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536352">DrmForwardContentToFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536568">IDrmAudioStream</a>
 

 

