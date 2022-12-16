---
UID: NF:acxstreams.AcxStreamGetElementsCount
tech.root: audio
title: AcxStreamGetElementsCount
ms.date: 12/16/2022
targetos: Windows
description: The AcxStreamGetElementsCount function retrieves the number of elements for the specified audio stream.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxStreamGetElementsCount
f1_keywords:
 - AcxStreamGetElementsCount
 - acxstreams/AcxStreamGetElementsCount
dev_langs:
 - c++
helpviewer_keywords:
 - AcxStreamGetElementsCount
---

## -description

The **AcxStreamGetElementsCount** function retrieves the number of elements for the specified audio stream.

## -parameters

### -param Stream [in]

The ACX stream object for which to retrieve the number of audio streams.

## -returns

Returns the number of elements for the object specified by the *Stream* parameter.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
