---
UID: NF:acxtargets.AcxTargetStreamAssignDrmContentId
tech.root: audio
title: AcxTargetStreamAssignDrmContentId
ms.date: 07/22/2022
targetos: Windows
description: The AcxTargetStreamAssignDrmContentId function given an existing ACXTARGETSTREAM object, assigns a DRM Content Id to that stream.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetStreamAssignDrmContentId
f1_keywords:
 - AcxTargetStreamAssignDrmContentId
 - acxtargets/AcxTargetStreamAssignDrmContentId
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamAssignDrmContentId** function given an existing ACXTARGETSTREAM object, assigns a DRM Content ID to that stream.

## -parameters

### -param TargetStream

An existing ACXTARGETSTREAM object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ContentId

Specifies the DRM content ID. This parameter is an identifier that the DRM system generates at run time to identify DRM-protected content in this stream.

### -param DrmRights

Pointer to a DRMRIGHTS structure specifying the rights granted by the content provider to the user for playing and copying DRM-protected content in this stream.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
 
