---
UID: NS:drmk.__unnamed_struct_1
title: KSP_DRMAUDIOSTREAM_CONTENTID (drmk.h)
description: The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions.
old-location: audio\ksp_drmaudiostream_contentid.htm
tech.root: audio
ms.assetid: 16a83c46-c183-4dc2-9d98-877976cf5750
ms.date: 05/08/2018
keywords: ["KSP_DRMAUDIOSTREAM_CONTENTID structure"]
ms.keywords: "*PKSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID structure [Audio Devices], PKSP_DRMAUDIOSTREAM_CONTENTID, PKSP_DRMAUDIOSTREAM_CONTENTID structure pointer [Audio Devices], aud-prop_f18ac59e-1ebf-4e98-8bab-1f54f76c6a64.xml, audio.ksp_drmaudiostream_contentid, drmk/KSP_DRMAUDIOSTREAM_CONTENTID, drmk/PKSP_DRMAUDIOSTREAM_CONTENTID"
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
f1_keywords:
 - PKSP_DRMAUDIOSTREAM_CONTENTID
 - drmk/PKSP_DRMAUDIOSTREAM_CONTENTID
 - KSP_DRMAUDIOSTREAM_CONTENTID
 - drmk/KSP_DRMAUDIOSTREAM_CONTENTID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - drmk.h
api_name:
 - KSP_DRMAUDIOSTREAM_CONTENTID
---

# KSP_DRMAUDIOSTREAM_CONTENTID structure


## -description

The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a <a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request. It also specifies a list of function pointers to the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/drm-functions">DRM functions</a>.

## -struct-fields

### -field Property

Specifies the property to get or set. This member is a structure of type <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>.

### -field Context

Pointer to context data. This is the context specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a> function's <i>DrmForward</i> parameter.

### -field DrmAddContentHandlers

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a> function.

### -field DrmCreateContentMixed

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a> function.

### -field DrmDestroyContent

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a> function.

### -field DrmForwardContentToDeviceObject

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a> function.

### -field DrmForwardContentToFileObject

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a> function.

### -field DrmForwardContentToInterface

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a> function.

### -field DrmGetContentRights

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights">DrmGetContentRights</a> function.

## -remarks

The structure contains function pointers to the DRM library functions in order to provide the driver with convenient access to these functions.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmaddcontenthandlers">DrmAddContentHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmcreatecontentmixed">DrmCreateContentMixed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmdestroycontent">DrmDestroyContent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttodeviceobject">DrmForwardContentToDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttofileobject">DrmForwardContentToFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmforwardcontenttointerface">DrmForwardContentToInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/drmk/nf-drmk-drmgetcontentrights">DrmGetContentRights</a>



<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/previous-versions/ff537351(v=vs.85)">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>

