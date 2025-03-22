---
UID: NF:ntifs.RtlGetAcesBufferSize
tech.root: ifsk
title: RtlGetAcesBufferSize
ms.date: 11/03/2023
targetos: Windows
description: Learn more about the RtlGetAcesBufferSize function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: IRQL <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - RtlGetAcesBufferSize
f1_keywords:
 - RtlGetAcesBufferSize
 - ntifs/RtlGetAcesBufferSize
dev_langs:
 - c++
helpviewer_keywords:
 - RtlGetAcesBufferSize
---

# RtlGetAcesBufferSize function (ntifs.h)

## -description

**RtlGetAcesBufferSize** computes the size of the access control entries (ACEs) for the specified access control list (ACL).

## -parameters

### -param Acl

[in] Pointer to the ACL to be queried.

### -param AcesBufferSize

[out] Receives the size of the buffer used to store the ACEs in the ACL.

## -returns

**RtlGetAcesBufferSize** returns STATUS_SUCCESS upon success. It returns STATUS_INVALID_PARAMETER if **Acl** or **AcesBufferSize** are NULL.
