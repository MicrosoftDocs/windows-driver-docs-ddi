---
UID: NF:acxstreams.AcxDrmGetContentRights
tech.root: audio
title: AcxDrmGetContentRights
ms.date: 07/01/2021
targetos: Windows
description: The AcxDrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID.
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
 - AcxDrmGetContentRights
f1_keywords:
 - AcxDrmGetContentRights
 - acxstreams/AcxDrmGetContentRights
dev_langs:
 - c++
---

## -description

The AcxDrmGetContentRights function retrieves the DRM content rights assigned to a DRM content ID.

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to an ACX audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.

### -param DrmRights

Specifies the DRM content rights that are assigned to the stream that is identified by ContentId. This parameter is a pointer to a [ACXDRMRIGHTS structure](ns-acxstreams-acxdrmrights.md).

## -returns

AcxDrmGetContentRights returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

## -see-also

- [acxstreams.h header](index.md)

READY2GO