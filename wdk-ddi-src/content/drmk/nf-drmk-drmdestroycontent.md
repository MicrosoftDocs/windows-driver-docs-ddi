---
UID: NF:drmk.DrmDestroyContent
title: DrmDestroyContent function (drmk.h)
description: The DrmDestroyContent function deletes a DRM content ID that was created by DrmCreateContentMixed.
old-location: audio\drmdestroycontent.htm
tech.root: audio
ms.assetid: 197f74f8-050e-4b0b-a95d-f640c565c17e
ms.date: 05/08/2018
keywords: ["DrmDestroyContent function"]
ms.keywords: DrmDestroyContent, DrmDestroyContent function [Audio Devices], aud-prop2_cfaec95c-a7e5-4488-a56d-323ebc577d90.xml, audio.drmdestroycontent, drmk/DrmDestroyContent
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DrmDestroyContent
 - drmk/DrmDestroyContent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Drmk.lib
 - Drmk.dll
api_name:
 - DrmDestroyContent
---

# DrmDestroyContent function


## -description

The <code>DrmDestroyContent</code> function deletes a DRM content ID that was created by <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>.

## -parameters

### -param ContentId 

[in]
Specifies a nonzero DRM content ID assigned to a KS audio stream by <b>DrmCreateContentMixed</b>. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.

## -returns

<b>DrmCreateContentMixed</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

A KS audio filter can only use <code>DrmDestroyContent</code> to delete a DRM content ID that it obtained by calling <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>. Note that a KS audio filter must not use <code>DrmDestroyContent</code> to delete a DRM content ID set by <a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-idrmaudiostream-setcontentid">IDrmAudioStream::SetContentId</a> or by an IOCTL_KS_PROPERTY request that sets the <a href="/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> property. Only the KS audio filter that created the content ID should delete it.

<code>DrmDestroyContent</code> performs the same function as <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdestroycontent">PcDestroyContent</a> and <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-idrmport-destroycontent">IDrmPort::DestroyContent</a>. For more information, see <a href="/windows-hardware/drivers/audio/drm-functions-and-interfaces">DRM Functions and Interfaces</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights">DrmGetContentRights</a>



<a href="/windows-hardware/drivers/ddi/drmk/nf-drmk-idrmaudiostream-setcontentid">IDrmAudioStream::SetContentId</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-idrmport-destroycontent">IDrmPort::DestroyContent</a>



<a href="/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcdestroycontent">PcDestroyContent</a>