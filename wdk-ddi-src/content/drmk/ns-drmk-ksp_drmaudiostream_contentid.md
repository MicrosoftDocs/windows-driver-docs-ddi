---
UID: NS:drmk.KSP_DRMAUDIOSTREAM_CONTENTID
title: KSP_DRMAUDIOSTREAM_CONTENTID
author: windows-driver-content
description: The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions.
old-location: audio\ksp_drmaudiostream_contentid.htm
old-project: audio
ms.assetid: 16a83c46-c183-4dc2-9d98-877976cf5750
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PKSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID structure [Audio Devices], PKSP_DRMAUDIOSTREAM_CONTENTID, PKSP_DRMAUDIOSTREAM_CONTENTID structure pointer [Audio Devices], aud-prop_f18ac59e-1ebf-4e98-8bab-1f54f76c6a64.xml, audio.ksp_drmaudiostream_contentid, drmk/KSP_DRMAUDIOSTREAM_CONTENTID, drmk/PKSP_DRMAUDIOSTREAM_CONTENTID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	drmk.h
api_name:
-	KSP_DRMAUDIOSTREAM_CONTENTID
product:
- Windows
targetos: Windows
req.typenames: KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
---

# KSP_DRMAUDIOSTREAM_CONTENTID structure


## -description


The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request. It also specifies a list of function pointers to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a>.


## -struct-fields




### -field Property

Specifies the property to get or set. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.


### -field Context

Pointer to context data. This is the context specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function's <i>DrmForward</i> parameter.


### -field DrmAddContentHandlers

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a> function.


### -field DrmCreateContentMixed

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a> function.


### -field DrmDestroyContent

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a> function.


### -field DrmForwardContentToDeviceObject

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function.


### -field DrmForwardContentToFileObject

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536352">DrmForwardContentToFileObject</a> function.


### -field DrmForwardContentToInterface

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a> function.


### -field DrmGetContentRights

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a> function.


## -remarks



The structure contains function pointers to the DRM library functions in order to provide the driver with convenient access to these functions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536347">DrmAddContentHandlers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536348">DrmCreateContentMixed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536352">DrmForwardContentToFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
 

 

