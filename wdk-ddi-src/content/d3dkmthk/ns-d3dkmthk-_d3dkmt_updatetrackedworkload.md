---
UID: NS:d3dkmthk._D3DKMT_UPDATETRACKEDWORKLOAD
title: _D3DKMT_UPDATETRACKEDWORKLOAD (d3dkmthk.h)
description: Arguments used to update the tracked workload.
ms.assetid: 7a3a3f6b-77a4-493b-a137-68fa57dc91de
ms.date: 10/19/2018
f1_keywords:
 - "d3dkmthk/_D3DKMT_UPDATETRACKEDWORKLOAD"
ms.keywords: _D3DKMT_UPDATETRACKEDWORKLOAD, D3DKMT_UPDATETRACKEDWORKLOAD, 
req.header: d3dkmthk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DKMT_UPDATETRACKEDWORKLOAD
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_UPDATETRACKEDWORKLOAD
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# _D3DKMT_UPDATETRACKEDWORKLOAD structure

## -description

Arguments used to update the tracked workload.

## -struct-fields

### -field hDevice

A handle to a device.

### -field hTrackedWorkload

A handle to a tracked workload.

### -field FinishDeadline

Specifies the deadline by which this workload should be finished.

### -field BeginTrackedWorkloadIndex

The index for the timestamp on the start of this workload pair (the index in the buffer pointed to by *hResourceQueryTimestamps* in the [_D3DKMT_CREATETRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_createtrackedworkload.md) structure).

### -field EndTrackedWorkloadIndex

The index for the timestamp at the end of this workload pair (the index in buffer pointed to by *hResourceQueryTimestamps* in the [_D3DKMT_CREATETRACKEDWORKLOAD](ns-d3dkmthk-_d3dkmt_createtrackedworkload.md) structure).

### -field FenceSubmissionValue

The fence value for the submission of this workload.

### -field FenceCompletedValue

The fence value for the completed workloads.

### -field GPUTimestampFrequency

The GPU timestamp frequency for resolving query timestamps.

### -field GPUCalibrationTimestamp

The value of the GPU calibration timestamp counter.

### -field CPUCalibrationTimestamp
 
The value of the CPU calibration timestamp counter.

## -remarks

## -see-also
