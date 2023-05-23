---
UID: NF:d3dkmthk.D3DKMTNotifyWorkSubmission
tech.root: display
title: D3DKMTNotifyWorkSubmission
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DKMTNotifyWorkSubmission function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.idl: 
req.include-header: 
req.irql:
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTNotifyWorkSubmission
f1_keywords:
 - D3DKMTNotifyWorkSubmission
 - d3dkmthk/D3DKMTNotifyWorkSubmission
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTNotifyWorkSubmission
---

## -description

**D3DKMTNotifyWorkSubmission** notifies the kernel-mode display driver that the user-mode display driver has submitted work to the GPU.

## -parameters

### -param unnamedParam1

Pointer to a [**D3DKMT_NOTIFY_WORK_SUBMISSION**](ns-d3dkmthk-_d3dkmt_notify_work_submission.md) structure that identifies the hardware queue on which the work was submitted.

## -returns

**D3DKMTNotifyWorkSubmission** returns STATUS_SUCCESS if it succeeds in pinging KMD. Otherwise, it returns an appropriate error code such as STATUS_INVALID_PARAMETER if an invalid hardware queue or flag are specified.

## -remarks

KMD can specify the doorbell connection status as D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY at [doorbell creation time](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md). Whenever UMD sees this doorbell status, it adjusts its work submission workflow such that after writing a new command and ringing the doorbell, it calls into the kernel using **D3DKMTNotifyWorkSubmission**. *Dxgkrnl* forwards this call to KMD using [**DxgkDdiNotifyWorkSubmission**](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md).

KMD can also request notification dynamically after doorbell creation. If KMD detects a condition where it should be notified of work submission on this hardware queue, then it can first disconnect the doorbell by calling *Dxgkrnl*'s [**DxgkCbDisconnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md) with status D3DDDI_DOORBELL_STATUS_DISCONNECTED_RETRY. Later, when UMD tries to reconnect the doorbell, KMD can make the connection with status D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY.

See [**DxgkDdiNotifyWorkSubmission**](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md) for details on how and when KMD should use this functionality.

## -see-also

[**D3DKMT_NOTIFY_WORK_SUBMISSION**](ns-d3dkmthk-_d3dkmt_notify_work_submission.md)

[**DxgkDdiNotifyWorkSubmission**](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md)
