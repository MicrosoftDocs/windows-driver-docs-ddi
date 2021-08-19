---
UID: NF:acxstreams.AcxDrmCreateContentMixed
tech.root: audio
title: AcxDrmCreateContentMixed
ms.date:  06/16/2021
targetos: Windows
description: The AcxCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef 
api_location:
 - acxstreams.h
api_name:
 - AcxDrmCreateContentMixed
f1_keywords:
 - AcxDrmCreateContentMixed
 - acxstreams/AcxDrmCreateContentMixed
dev_langs:
 - c++
---

## -description

The AcxCreateContentMixed function creates a DRM content ID to identify a KS audio stream containing mixed content from a number of streams

## -parameters

### -param paContentId

Pointer to an array of DRM content IDs. Each array element is of type ULONG and contains a content ID that represents a protected KS audio stream. If cContentId is zero, paContentID can be NULL. A content ID of zero is a special value that represents an audio stream with default DRM content rights (see DEFINE_DRMRIGHTS_DEFAULT).

### -param cContentId

Specifies the number of DRM content IDs in the paContentId array. The array can hold zero or more content IDs.

### -param pMixedContentId

Output pointer for the composite content ID. This parameter points to a caller-allocated ULONG variable into which the function writes the new content ID for the composite KS audio stream. If cContentId is zero, the function assigns default DRM content rights to the new content ID.

## -returns

AcxDrmCreateContentMixed returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

TBD -> Code Example?

```cpp

```

## -see-also

[AcxDrmDestroyContent](nf-acxstreams-acxdrmdestroycontent.md)

[acxstreams.h header](index.md)

