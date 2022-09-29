---
UID: NF:acxstreams.AcxDrmRetrieveContentRights
tech.root: audio
title: AcxDrmRetrieveContentRights
ms.date: 09/28/2022
targetos: Windows
description: The AcxDrmRetrieveContentRights function gets the DRM content rights assigned to a DRM content ID.
prerelease: false
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
 - AcxDrmRetrieveContentRights
f1_keywords:
 - AcxDrmRetrieveContentRights
 - acxstreams/AcxDrmRetrieveContentRights
dev_langs:
 - c++
helpviewer_keywords:
 - AcxDrmRetrieveContentRights
---

## -description

The **AcxDrmRetrieveContentRights** function gets the DRM content rights assigned to a DRM content ID.

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to an ACX audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). A content ID of zero represents an audio stream with default DRM content rights and cannot be used with this function.

### -param DrmRights

Specifies the DRM content rights that are assigned to the stream that is identified by *ContentId*. This parameter is a pointer to an [ACXDRMRIGHTS](ns-acxstreams-acxdrmrights.md) structure.

## -returns

**AcxDrmRetrieveContentRights** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
