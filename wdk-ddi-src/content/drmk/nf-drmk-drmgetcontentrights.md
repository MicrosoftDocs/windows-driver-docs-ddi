---
UID: NF:drmk.DrmGetContentRights
title: DrmGetContentRights function
author: windows-driver-content
description: The DrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID.
old-location: audio\drmgetcontentrights.htm
old-project: audio
ms.assetid: 706a5749-e288-4275-84fc-e500a848d541
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: aud-prop2_9f836831-bb65-45d1-8701-4aaa77999b81.xml, DrmGetContentRights, drmk/DrmGetContentRights, DrmGetContentRights function [Audio Devices], audio.drmgetcontentrights
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Drmk.lib
-	Drmk.dll
apiname:
-	DrmGetContentRights
product: Windows
targetos: Windows
req.typenames: "*PWDI_TX_METADATA, WDI_TX_METADATA"
---

# DrmGetContentRights function


## -description


The <code>DrmGetContentRights</code> function retrieves the DRM content rights assigned to a DRM content ID.


## -syntax


````
NTSTATUS DrmGetContentRights(
  _In_  ULONG      ContentId,
  _Out_ PDRMRIGHTS DrmRights
);
````


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a KS audio stream.


### -param DrmRights [out]

Specifies the DRM content rights that are assigned to the stream that is identified by <i>ContentId</i>. This parameter is a pointer to a <a href="..\drmk\ns-drmk-tagdrmrights.md">DRMRIGHTS</a> structure.


## -returns


<code>DrmGetContentRights</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


Before a KS audio filter begins mixing together several KS audio streams, it first calls <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a> to create a content ID for the composite stream. Next, it calls <code>DrmGetContentRights</code> to get the content rights that the system has assigned to the stream.

A module that lies downstream from the KS filter that creates the content ID typically does not need to call <code>DrmGetContentRights</code>. Instead, the module receives both the content ID and content rights either from the system (through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a> call or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request) or directly from the preceding module in the data path (through a call to a content handler). For more information, see <a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>, <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>, and <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>.

<code>DrmGetContentRights</code> performs the same function as <a href="..\portcls\nf-portcls-pcgetcontentrights.md">PcGetContentRights</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536588">IDrmPort::GetContentRights</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536588">IDrmPort::GetContentRights</a>

<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>

<a href="..\portcls\nf-portcls-pcgetcontentrights.md">PcGetContentRights</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>

<a href="..\drmk\ns-drmk-tagdrmrights.md">DRMRIGHTS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536570">IDrmAudioStream::SetContentId</a>

<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmGetContentRights function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

