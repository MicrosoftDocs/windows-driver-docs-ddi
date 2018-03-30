---
UID: NF:drmk.DrmCreateContentMixed
title: DrmCreateContentMixed function
author: windows-driver-content
description: The DrmCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams.
old-location: audio\drmcreatecontentmixed.htm
old-project: audio
ms.assetid: cec501d9-17e3-46a1-929e-4f9ba35ba721
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: DrmCreateContentMixed, DrmCreateContentMixed function [Audio Devices], aud-prop2_19a8815e-db9d-43a9-ad5a-c081a1af4f99.xml, audio.drmcreatecontentmixed, drmk/DrmCreateContentMixed
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
-	DrmCreateContentMixed
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# DrmCreateContentMixed function


## -description


The <code>DrmCreateContentMixed</code> function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams.


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

After obtaining a content ID from <code>DrmCreateContentMixed</code>, the caller can get the content rights assigned to the content ID by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>.

After a change to the content rights of any of the components of a composite audio stream, the KS audio filter that mixes the stream must call <code>DrmCreateContentMixed</code> to obtain a new content ID for the composite audio stream. <code>DrmCreateContentMixed</code> determines the most restrictive of the content rights that are assigned to the individual content IDs specified in the <i>paContentId</i> array and assigns these rights to the new content ID.

After a KS audio filter finishes using a content ID that it created using <code>DrmCreateContentMixed</code>, the filter must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a> to delete the content ID. However, before deleting an old content ID, the KS audio filter must first successfully forward a new content ID to all the streams to which it previously forwarded the old content ID. The KS audio filter forwards a content ID by calling a <b>DrmForwardContentTo</b><i>Xxx</i> function.

<code>DrmCreateContentMixed</code> performs the same function as <a href="https://msdn.microsoft.com/library/windows/hardware/ff537689">PcCreateContentMixed</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536581">IDrmPort::CreateContentMixed</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536254">DEFINE_DRMRIGHTS_DEFAULT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536349">DrmDestroyContent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536353">DrmForwardContentToInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536581">IDrmPort::CreateContentMixed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537689">PcCreateContentMixed</a>
 

 

