---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT
ms.date: 07/26/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT function initializes ACX_REQUEST_PARAMETERS struct.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
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
 - LibDef
api_location:
 - acxrequest.h
api_name:
 - ACX_REQUEST_PARAMETERS_INIT
f1_keywords:
 - ACX_REQUEST_PARAMETERS_INIT
 - acxrequest/ACX_REQUEST_PARAMETERS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_PARAMETERS_INIT** function initializes an ACX_REQUEST_PARAMETERS struct.

## -parameters

### -param Parameters

An [ACX_REQUEST_PARAMETERS](nf-acxrequest-acxrequestgetparameters.md) structure that stores the ACX/KS operation parameters.

## -remarks

### Example

Example usage is shown below.

```cpp

    ACX_REQUEST_PARAMETERS params;

    ACX_REQUEST_PARAMETERS_INIT(&params);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
