---
UID: NS:d3dkmthk._D3DKMT_NOTIFY_WORK_SUBMISSION
tech.root: display
title: D3DKMT_NOTIFY_WORK_SUBMISSION
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the D3DKMT_NOTIFY_WORK_SUBMISSION structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_NOTIFY_WORK_SUBMISSION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_NOTIFY_WORK_SUBMISSION
 - D3DKMT_NOTIFY_WORK_SUBMISSION
f1_keywords:
 - _D3DKMT_NOTIFY_WORK_SUBMISSION
 - d3dkmthk/_D3DKMT_NOTIFY_WORK_SUBMISSION
 - D3DKMT_NOTIFY_WORK_SUBMISSION
 - d3dkmthk/D3DKMT_NOTIFY_WORK_SUBMISSION
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_NOTIFY_WORK_SUBMISSION
---

# D3DKMT_NOTIFY_WORK_SUBMISSION structure (d3dkmthk.h)

## -description

The **D3DKMT_NOTIFY_WORK_SUBMISSION** structure is passed to [**D3DKMTNotifyWorkSubmission**](nf-d3dkmthk-d3dkmtnotifyworksubmission.md) to notify the kernel-mode display driver (KMD) that the user-mode display driver (UMD) has submitted work to the GPU.

## -struct-fields

### -field hDoorbell

[in] UM handle of the doorbell. This handle was returned in a prior call to [**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md).

### -field Flags

[in] A [**D3DKMT_NOTIFY_WORK_SUBMISSION_FLAGS**](ns-d3dkmthk-d3dkmt_notify_work_submission_flags.md) structure with work submission flags.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**D3DKMT_NOTIFY_WORK_SUBMISSION_FLAGS**](ns-d3dkmthk-d3dkmt_notify_work_submission_flags.md)

[**D3DKMTNotifyWorkSubmission**](nf-d3dkmthk-d3dkmtnotifyworksubmission.md)
