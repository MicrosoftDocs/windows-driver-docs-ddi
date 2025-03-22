---
UID: NF:d3dkmthk.D3DKMTNotifyWorkSubmission
tech.root: display
title: D3DKMTNotifyWorkSubmission
ms.date: 04/08/2024
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
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

# D3DKMTNotifyWorkSubmission function (d3dkmthk.h)

## -description

**D3DKMTNotifyWorkSubmission** notifies the kernel-mode display driver (KMD) that the user-mode display driver (UMD) has submitted work to the GPU.

## -parameters

### -param unnamedParam1

Pointer to a [**D3DKMT_NOTIFY_WORK_SUBMISSION**](ns-d3dkmthk-d3dkmt_notify_work_submission.md) structure that identifies the hardware queue on which the work was submitted.

## -returns

**D3DKMTNotifyWorkSubmission** returns STATUS_SUCCESS if it succeeds in pinging KMD. Otherwise, it returns an appropriate error code such as STATUS_INVALID_PARAMETER if an invalid hardware queue or flag are specified.

## -remarks

In the [user-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission) model, KMD isn't involved in work submission and so isn't aware when new work is submitted on a HWQueue. This low latency work submission path is the main motivation of the model. However, there are certain niche scenarios and hardware limitations when KMD needs to be notified whenever work is submitted on a HWQueue. For example, a GPU hardware scheduler requires KMD to switch the hardware runlist from normal to realtime when a realtime context submits work. If KMD isn't involved in work submission then it can't trigger the runlist switch immediately, which results in delaying the realtime work execution.

To accommodate this need, KMD can specify the doorbell connection status as D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY at [doorbell creation time](nf-d3dkmthk-d3dkmtcreatedoorbell.md). Whenever UMD sees this doorbell status, it adjusts its work submission workflow such that after writing a new command and ringing the doorbell, it calls into the kernel using **D3DKMTNotifyWorkSubmission**. *Dxgkrnl* forwards this call to KMD using [**DxgkDdiNotifyWorkSubmission**](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md).

**D3DKMTNotifyWorkSubmission** is a simple ping from UMD to *Dxgkrnl* to KMD, notifying the latter that new work has been submitted on a particular HWQueue so that KMD can initiate specific actions such as switching a runlist to realtime.

KMD can also request notification dynamically after doorbell creation. If KMD detects a condition where it should be notified of work submission on this hardware queue, then it can first disconnect the doorbell by calling *Dxgkrnl*'s [**DxgkCbDisconnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md) with status D3DDDI_DOORBELL_STATUS_DISCONNECTED_RETRY. Later, when UMD tries to reconnect the doorbell, KMD can make the connection with status D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY.

Drivers should use this mechanism in very specific and infrequent scenarios because it involves a round trip from UMD to KMD on every work submission, and if it is used for broad scenarios then it defeats the purpose of a low latency user mode submission model.

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**D3DKMT_NOTIFY_WORK_SUBMISSION**](ns-d3dkmthk-d3dkmt_notify_work_submission.md)

[**D3DKMTCreateDoorbell**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**DxgkCbDisconnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md)

[**DxgkDdiNotifyWorkSubmission**](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md)
