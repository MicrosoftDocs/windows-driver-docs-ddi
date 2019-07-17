---
UID: NF:drmk.DrmGetContentRights
title: DrmGetContentRights function (drmk.h)
description: The DrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID.
old-location: audio\drmgetcontentrights.htm
tech.root: audio
ms.assetid: 706a5749-e288-4275-84fc-e500a848d541
ms.date: 05/08/2018
ms.keywords: DrmGetContentRights, DrmGetContentRights function [Audio Devices], aud-prop2_9f836831-bb65-45d1-8701-4aaa77999b81.xml, audio.drmgetcontentrights, drmk/DrmGetContentRights
ms.topic: function
f1_keywords:
 - "drmk/DrmGetContentRights"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Drmk.lib
- Drmk.dll
api_name:
- DrmGetContentRights
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrmGetContentRights function


## -description


The <code>DrmGetContentRights</code> function retrieves the DRM content rights assigned to a DRM content ID.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a KS audio stream.


### -param DrmRights [out]

Specifies the DRM content rights that are assigned to the stream that is identified by <i>ContentId</i>. This parameter is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a> structure.


## -returns



<code>DrmGetContentRights</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



Before a KS audio filter begins mixing together several KS audio streams, it first calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a> to create a content ID for the composite stream. Next, it calls <code>DrmGetContentRights</code> to get the content rights that the system has assigned to the stream.

A module that lies downstream from the KS filter that creates the content ID typically does not need to call <code>DrmGetContentRights</code>. Instead, the module receives both the content ID and content rights either from the system (through an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-idrmaudiostream-setcontentid">IDrmAudioStream::SetContentId</a> call or a <a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request) or directly from the preceding module in the data path (through a call to a content handler). For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a>.

<code>DrmGetContentRights</code> performs the same function as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcgetcontentrights">PcGetContentRights</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-idrmport-getcontentrights">IDrmPort::GetContentRights</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/drm-functions-and-interfaces">DRM Functions and Interfaces</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/ns-drmk-tagdrmrights">DRMRIGHTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/drmk/nf-drmk-idrmaudiostream-setcontentid">IDrmAudioStream::SetContentId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-idrmport-getcontentrights">IDrmPort::GetContentRights</a>



<a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcgetcontentrights">PcGetContentRights</a>
 

 

