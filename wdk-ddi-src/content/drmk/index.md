---
UID: NA:drmk
ms.assetid: d0869a59-50dc-35f9-a3cc-2e955c1a9812
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Drmk.h header



This header is used by Audio. For more information, see
- [Audio](../_audio/index.md)

Drmk.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [DrmAddContentHandlers function](nf-drmk-drmaddcontenthandlers.md) | The DrmAddContentHandlers function provides the system with a list of functions that handle protected content. |
| [DrmCreateContentMixed function](nf-drmk-drmcreatecontentmixed.md) | The DrmCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams. |
| [DrmDestroyContent function](nf-drmk-drmdestroycontent.md) | The DrmDestroyContent function deletes a DRM content ID that was created by DrmCreateContentMixed. |
| [DrmForwardContentToDeviceObject function](nf-drmk-drmforwardcontenttodeviceobject.md) | The DrmForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content. |
| [DrmForwardContentToFileObject function](nf-drmk-drmforwardcontenttofileobject.md) | The DrmForwardContentToFileObject function is obsolete and is maintained only to support existing drivers. |
| [DrmForwardContentToInterface function](nf-drmk-drmforwardcontenttointerface.md) | The DrmForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. |
| [DrmGetContentRights function](nf-drmk-drmgetcontentrights.md) | The DrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFNDRMADDCONTENTHANDLERS callback](nc-drmk-pfndrmaddcontenthandlers.md) | This callback function is reserved for system use. |
| [PFNDRMCREATECONTENTMIXED callback](nc-drmk-pfndrmcreatecontentmixed.md) | This callback function is reserved for system use. |
| [PFNDRMDESTROYCONTENT callback](nc-drmk-pfndrmdestroycontent.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTODEVICEOBJECT callback](nc-drmk-pfndrmforwardcontenttodeviceobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOFILEOBJECT callback](nc-drmk-pfndrmforwardcontenttofileobject.md) | This callback function is reserved for system use. |
| [PFNDRMFORWARDCONTENTTOINTERFACE callback](nc-drmk-pfndrmforwardcontenttointerface.md) | This callback function is reserved for system use. |
| [PFNDRMGETCONTENTRIGHTS callback](nc-drmk-pfndrmgetcontentrights.md) | This callback function is reserved for system use. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [KSDRMAUDIOSTREAM_CONTENTID structure](ns-drmk-ksdrmaudiostream_contentid.md) | The KSDRMAUDIOSTREAM_CONTENTID structure specifies the DRM content ID and DRM content rights for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. |
| [KSP_DRMAUDIOSTREAM_CONTENTID structure](ns-drmk-ksp_drmaudiostream_contentid.md) | The KSP_DRMAUDIOSTREAM_CONTENTID structure specifies the property, request type, and context for a KSPROPERTY_DRMAUDIOSTREAM_CONTENTIDset-property request. It also specifies a list of function pointers to the DRM functions. |
| [tagDRMFORWARD structure](ns-drmk-tagdrmforward.md) | The DRMFORWARD structure contains the information that the DRMK system driver needs in order to forward a DRM content ID to a device that handles protected content. |
| [tagDRMRIGHTS structure](ns-drmk-tagdrmrights.md) | The DRMRIGHTS structure specifies the DRM content rights assigned to a KS audio pin or to a port-class driver's stream object. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IDrmAudioStream interface](nn-drmk-idrmaudiostream.md) | The IDrmAudioStream interface assigns DRM protection to the digital content in an audio stream. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IDrmAudioStream::SetContentId method](nf-drmk-idrmaudiostream-setcontentid.md) | The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream. |
