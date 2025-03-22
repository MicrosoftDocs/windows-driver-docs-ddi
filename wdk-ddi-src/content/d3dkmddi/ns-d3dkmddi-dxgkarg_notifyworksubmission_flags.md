---
UID: NS:d3dkmddi._DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
tech.root: display
title: DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the DXGKARG_NOTIFYWORKSUBMISSION_FLAGS structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
 - DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
f1_keywords:
 - _DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
 - d3dkmddi/_DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
 - DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
 - d3dkmddi/DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_NOTIFYWORKSUBMISSION_FLAGS
---

# DXGKARG_NOTIFYWORKSUBMISSION_FLAGS structure (d3dkmddi.h)

## -description

The **DXGKARG_NOTIFYWORKSUBMISSION_FLAGS** structure specifies work submission flags for [**DxgkDdiNotifyWorkSubmission**](nc-d3dkmddi-dxgkddi_notifyworksubmission.md).

## -struct-fields

### -field Reserved

Reserved; set to zero.

### -field Value

An alternative way to access the structure members.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**DXGKARG_NOTIFYWORKSUBMISSION**](ns-d3dkmddi-dxgkarg_notifyworksubmission.md)

[**DxgkDdiNotifyWorkSubmission**](nc-d3dkmddi-dxgkddi_notifyworksubmission.md)
