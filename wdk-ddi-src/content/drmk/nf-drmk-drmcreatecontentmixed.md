---
UID: NF:drmk.DrmCreateContentMixed
title: DrmCreateContentMixed function
author: windows-driver-content
description: The DrmCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams.
old-location: audio\drmcreatecontentmixed.htm
old-project: audio
ms.assetid: cec501d9-17e3-46a1-929e-4f9ba35ba721
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.drmcreatecontentmixed, aud-prop2_19a8815e-db9d-43a9-ad5a-c081a1af4f99.xml, DrmCreateContentMixed, DrmCreateContentMixed function [Audio Devices], drmk/DrmCreateContentMixed
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
-	DrmCreateContentMixed
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# DrmCreateContentMixed function


## -description


The <code>DrmCreateContentMixed</code> function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams.


## -syntax


````
NTSTATUS DrmCreateContentMixed(
  _In_  PULONG paContentId,
  _In_  ULONG  cContentId,
  _Out_ PULONG pMixedContentId
);
````


## -parameters




### -param paContentId [in]

Pointer to an array of DRM content IDs. Each array element is of type ULONG and contains a content ID that represents a protected KS audio stream. If <i>cContentId</i> is zero, <i>paContentID</i> can be <b>NULL</b>. A content ID of zero is a special value that represents an audio stream with default DRM content rights (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536254">DEFINE_DRMRIGHTS_DEFAULT</a>).


### -param cContentId [in]

Specifies the number of DRM content IDs in the <i>paContentId</i> array. The array can hold zero or more content IDs.


### -param pMixedContentId [out]

Output pointer for the composite content ID. This parameter points to a caller-allocated ULONG variable into which the function writes the new content ID for the composite KS audio stream. If <i>cContentId</i> is zero, the function assigns default DRM content rights to the new content ID.


## -returns


<code>DrmCreateContentMixed</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


A KS audio filter calls the <code>DrmCreateContentMixed</code> function to obtain a DRM content ID for a composite stream. The filter produces this stream by mixing together the KS audio streams whose content IDs are listed in the <i>paContentId</i> array. Given this list of content IDs for the streams at the mixer inputs, the function calculates the content rights of the composite stream and assigns a new content ID to that stream.

If the caller does not specify any content IDs (that is, if <i>cContentId</i> is zero), the function assigns default content rights to the content ID that it creates to identify the composite stream.

After obtaining a content ID from <code>DrmCreateContentMixed</code>, the caller can get the content rights assigned to the content ID by calling <a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>.

After a change to the content rights of any of the components of a composite audio stream, the KS audio filter that mixes the stream must call <code>DrmCreateContentMixed</code> to obtain a new content ID for the composite audio stream. <code>DrmCreateContentMixed</code> determines the most restrictive of the content rights that are assigned to the individual content IDs specified in the <i>paContentId</i> array and assigns these rights to the new content ID.

After a KS audio filter finishes using a content ID that it created using <code>DrmCreateContentMixed</code>, the filter must call <a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a> to delete the content ID. However, before deleting an old content ID, the KS audio filter must first successfully forward a new content ID to all the streams to which it previously forwarded the old content ID. The KS audio filter forwards a content ID by calling a <b>DrmForwardContentTo</b><i>Xxx</i> function.

<code>DrmCreateContentMixed</code> performs the same function as <a href="..\portcls\nf-portcls-pccreatecontentmixed.md">PcCreateContentMixed</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536581">IDrmPort::CreateContentMixed</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.



## -see-also

<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536254">DEFINE_DRMRIGHTS_DEFAULT</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>

<a href="..\portcls\nf-portcls-pccreatecontentmixed.md">PcCreateContentMixed</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536581">IDrmPort::CreateContentMixed</a>

<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmCreateContentMixed function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

