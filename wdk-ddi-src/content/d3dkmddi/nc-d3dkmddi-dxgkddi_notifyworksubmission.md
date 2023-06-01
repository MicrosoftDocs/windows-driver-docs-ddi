---
UID: NC:d3dkmddi.DXGKDDI_NOTIFYWORKSUBMISSION
tech.root: display
title: DXGKDDI_NOTIFYWORKSUBMISSION
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKDDI_NOTIFYWORKSUBMISSION callback function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
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
 - d3dkmddi.h
api_name:
 - DXGKDDI_NOTIFYWORKSUBMISSION
f1_keywords:
 - DXGKDDI_NOTIFYWORKSUBMISSION
 - d3dkmddi/DXGKDDI_NOTIFYWORKSUBMISSION
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_NOTIFYWORKSUBMISSION
---

## -description

The **DxgkDdiNotifyWorkSubmission** function notifies KMD that new work has been submitted.

## -parameters

### -param pArgs

[in] Pointer to a [**DXGKARG_NOTIFYWORKSUBMISSION**](ns-d3dkmddi-dxgkarg_notifyworksubmission.md) structure that identifies the hardware queue on which the work was submitted.

## -returns

**DxgkDdiNotifyWorkSubmission** must succeed and return STATUS_SUCCESS.

## -remarks

In the user-mode work submission model, KMD isn't involved in work submission and so isn't typically aware when new work is submitted on a hardware queue. This factor is the main motivation of a low latency work submission path. However, there are certain niche scenarios and hardware limitations in which KMD needs to be notified whenever work is submitted on a hardware queue. For example, a GPU hardware scheduler requires KMD to switch the hardware runlist from normal to real time when a real time context submits work. If KMD isn't involved in work submission then it can't trigger the runlist switch immediately, which results in delaying the real time work execution.

To solve this problem, KMD can specify the doorbell connection status as D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY at [doorbell creation time](nc-d3dkmddi-dxgkddi_createdoorbell.md). Whenever UMD sees this doorbell status, it adjusts its work submission workflow such that after writing a new command and ringing the doorbell, it calls into the kernel using [**D3DKMTNotifyWorkSubmission**](../d3dkmthk/nf-d3dkmthk-d3dkmtnotifyworksubmission.md). *Dxgkrnl* forwards this call to KMD via **DxgkDdiNotifyWorkSubmission**.

**DxgkDdiNotifyWorkSubmission** is a simple ping from UMD to *Dxgkrnl* to KMD, notifying the latter that new work has been submitted on a particular hardware queue, thus allowing KMD to initiate specific actions such as switching the runlist to real time.

KMD can also request notification dynamically after doorbell creation. If KMD detects a condition where it should be notified of work submission on this hardware queue, then it can first disconnect the doorbell using [**DxgkCbDisconnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md) with status D3DDDI_DOORBELL_STATUS_DISCONNECTED_RETRY. Later, when UMD tries to reconnect the doorbell, KMD can make the connection with status D3DDDI_DOORBELL_STATUS_CONNECTED_NOTIFY.

Drivers should use this mechanism in very specific and infrequent scenarios because it involves a round trip from UMD to KMD on every work submission, and if it is used for broad scenarios then it defeats the purpose of a low latency user mode submission model.

## -see-also

[**DXGKARG_NOTIFYWORKSUBMISSION**](ns-d3dkmddi-dxgkarg_notifyworksubmission.md)

[**DxgkDdiCreateDoorbell](nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**DxgkCbDisconnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkcb_disconnectdoorbell.md)
