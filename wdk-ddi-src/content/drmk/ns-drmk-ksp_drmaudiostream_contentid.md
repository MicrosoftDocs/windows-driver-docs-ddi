---
UID: NS:drmk.KSP_DRMAUDIOSTREAM_CONTENTID
title: KSP_DRMAUDIOSTREAM_CONTENTID
author: windows-driver-content
description: The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions.
old-location: audio\ksp_drmaudiostream_contentid.htm
old-project: audio
ms.assetid: 16a83c46-c183-4dc2-9d98-877976cf5750
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSP_DRMAUDIOSTREAM_CONTENTID, KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
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
req.alt-api: KSP_DRMAUDIOSTREAM_CONTENTID
req.alt-loc: drmk.h
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
req.typenames: KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID
---

# KSP_DRMAUDIOSTREAM_CONTENTID structure



## -description
The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request. It also specifies a list of function pointers to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM functions</a>.



## -syntax

````
typedef struct {
  KSPROPERTY                         Property;
  PVOID                              Context;
  PFNDRMADDCONTENTHANDLERS           DrmAddContentHandlers;
  PFNDRMCREATECONTENTMIXED           DrmCreateContentMixed;
  PFNDRMDESTROYCONTENT               DrmDestroyContent;
  PFNDRMFORWARDCONTENTTODEVICEOBJECT DrmForwardContentToDeviceObject;
  PFNDRMFORWARDCONTENTTOFILEOBJECT   DrmForwardContentToFileObject;
  PFNDRMFORWARDCONTENTTOINTERFACE    DrmForwardContentToInterface;
  PFNDRMGETCONTENTRIGHTS             DrmGetContentRights;
} KSP_DRMAUDIOSTREAM_CONTENTID, *PKSP_DRMAUDIOSTREAM_CONTENTID;
````


## -struct-fields

### -field Property

Specifies the property to get or set. This member is a structure of type <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>.


### -field Context

Pointer to context data. This is the context specified in the <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function's <i>DrmForward</i> parameter.


### -field DrmAddContentHandlers

Pointer to <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a> function.


### -field DrmCreateContentMixed

Pointer to <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a> function.


### -field DrmDestroyContent

Pointer to <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a> function.


### -field DrmForwardContentToDeviceObject

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function.


### -field DrmForwardContentToFileObject

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a> function.


### -field DrmForwardContentToInterface

Pointer to <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a> function.


### -field DrmGetContentRights

Pointer to <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a> function.


## -remarks
The structure contains function pointers to the DRM library functions in order to provide the driver with convenient access to these functions.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSP_DRMAUDIOSTREAM_CONTENTID structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

