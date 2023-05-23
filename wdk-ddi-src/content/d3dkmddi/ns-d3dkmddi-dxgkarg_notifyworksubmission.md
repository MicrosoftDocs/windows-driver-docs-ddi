---
UID: NS:d3dkmddi._DXGKARG_NOTIFYWORKSUBMISSION
tech.root: display
title: DXGKARG_NOTIFYWORKSUBMISSION
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_NOTIFYWORKSUBMISSION structure.
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
req.target-min-winverclnt: WIN11_FUTURE 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_NOTIFYWORKSUBMISSION
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
 - _DXGKARG_NOTIFYWORKSUBMISSION
 - DXGKARG_NOTIFYWORKSUBMISSION
f1_keywords:
 - _DXGKARG_NOTIFYWORKSUBMISSION
 - d3dkmddi/_DXGKARG_NOTIFYWORKSUBMISSION
 - DXGKARG_NOTIFYWORKSUBMISSION
 - d3dkmddi/DXGKARG_NOTIFYWORKSUBMISSION
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_NOTIFYWORKSUBMISSION
---

## -description

The **DXGKARG_NOTIFYWORKSUBMISSION** structure contains parameters for [**DxgkDdiNotifyWorkSubmission**](nc-d3dkmddi-dxgkddi_notifyworksubmission.md).

## -struct-fields

### -field hHwQueue

[in] Handle to a KMD hardware queue object, which was created in a previous call to KMD's [**DxgkDdiCreateHwQueue**](ns-d3dkmddi-dxgkddi_createhwqueue.md) callback function.

### -field Flags

[in] A bit field of [**DXGKARG_NOTIFYWORKSUBMISSION_FLAGS**](ns-d3dkmddi-dxgkarg_notifyworksubmission_flags.md) values that specify work submission flags.

## -see-also

 [**DXGKARG_NOTIFYWORKSUBMISSION_FLAGS**](ns-d3dkmddi-dxgkarg_notifyworksubmission_flags.md)

[**DxgkDdiNotifyWorkSubmission**](nc-d3dkmddi-dxgkddi_notifyworksubmission.md)
