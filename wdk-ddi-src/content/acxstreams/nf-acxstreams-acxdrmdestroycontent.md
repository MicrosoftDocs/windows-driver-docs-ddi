---
UID: NF:acxstreams.AcxDrmDestroyContent
tech.root: audio
title: AcxDrmDestroyContent
ms.date: 06/23/2021
targetos: Windows
description: The AcxDrmDestroyContent function deletes a DRM content ID that was created by AcxDrmCreateContentMixed.
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
 - AcxDrmDestroyContent
f1_keywords:
 - AcxDrmDestroyContent
 - acxstreams/AcxDrmDestroyContent
dev_langs:
 - c++
---

## -description

The AcxDrmDestroyContent function deletes a DRM content ID that was created by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md).

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to an ACX audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.

## -returns

AcxDrmDestroyContentMixed returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

## -see-also

- [acxstreams.h header](index.md)

READY2GO