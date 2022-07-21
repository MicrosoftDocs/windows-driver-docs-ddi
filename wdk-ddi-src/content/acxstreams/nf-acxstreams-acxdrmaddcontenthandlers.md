---
UID: NF:acxstreams.AcxDrmAddContentHandlers
tech.root: audio
title: AcxDrmAddContentHandlers
ms.date:  06/16/2021
targetos: Windows
description: The AcxDrmAddContentHandlers function provides the system with a list of functions that handle protected content.
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
 - AcxDrmAddContentHandlers
f1_keywords:
 - AcxDrmAddContentHandlers
 - acxstreams/AcxDrmAddContentHandlers
dev_langs:
 - c++
---

## -description

The AcxDrmAddContentHandlers function provides the system with a list of functions that handle protected content.

## -parameters

### -param ContentId

Specifies a nonzero DRM content ID assigned to an ACX audio stream by [AcxDrmCreateContentMixed](nf-acxstreams-acxdrmcreatecontentmixed.md). Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.

### -param paHandlers

Pointer to an array of function pointers. Each array element points to a content handler.

### -param NumHandlers

Specifies the number of function pointers in the paHandlers array.

## -returns

AcxDrmAddContentHandlers returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks


## -see-also

- [acxstreams.h header](index.md)

READY2GO