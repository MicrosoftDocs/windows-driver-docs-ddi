---
UID: NS:d3dkmthk._D3DKMT_NOTIFY_WORK_SUBMISSION
tech.root: display
title: D3DKMT_NOTIFY_WORK_SUBMISSION
ms.date: 05/22/2023
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
req.target-min-winverclnt: WIN11_FUTURE
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

## -description

The **D3DKMT_NOTIFY_WORK_SUBMISSION** structure identifies the hardware queue on which UMD submitted work.

## -struct-fields

### -field hHwQueue

[in] UMD handle of the hardware queue object created in a prior call to [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md). This object identifies the hardware queue on which work was submitted.

### -field Flags

[in] A [**D3DKMT_NOTIFY_WORK_SUBMISSION_FLAGS**](ns-d3dkmthk-d3dkmt_notify_work_submission_flags.md) structure with work submission flags.

## -see-also

[**D3DKMT_NOTIFY_WORK_SUBMISSION_FLAGS**](ns-d3dkmthk-d3dkmt_notify_work_submission_flags.md)

[**D3DKMTNotifyWorkSubmission**](nf-d3dkmthk-d3dkmtnotifyworksubmission.md)
