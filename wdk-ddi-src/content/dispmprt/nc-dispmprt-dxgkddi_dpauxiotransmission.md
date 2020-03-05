---
UID: NC:dispmprt.DXGKDDI_DPAUXIOTRANSMISSION
title: DXGKDDI_DPAUXIOTRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The DXGKDDI_DPAUXIOTRANSMISSION callback reads or writes DisplayPort Configuration Data (DPCD) for devices directly attached on the GPU.
req.assembly: 
eq.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
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
 - dispmprt.h
api_name:
 - DXGKDDI_DPAUXIOTRANSMISSION
f1_keywords:
 - dispmprt/DXGKDDI_DPAUXIOTRANSMISSION
dev_langs:
 - c++
---

# DXGKDDI_DPAUXIOTRANSMISSION callback function

## -description

The **DXGKDDI_DPAUXIOTRANSMISSION** callback reads or writes DisplayPort Configuration Data (DPCD) for devices directly attached on the GPU.

## -parameters

### -param Context

Context pointer provided when querying the interface.

### -param pArgs

Pointer to a [DXGKARG_DPAUXIOTRANSMISSION](ns-dispmprt-dxgkarg_dpauxiotransmission.md) structure.

## -returns

**DXGKDDI_DPAUXIOTRANSMISSION** returns STATUS_SUCCESS if it succeeds; otherwise it returns an error code such as one of the following:

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_DRIVER_INTERNAL_ERROR | An internal software error occurred.|  
| STATUS_ACCESS_DENIED | The request is not supported. For Windows 10 version 2004, only native AUX read is supported. |
| STATUS_BUFFER_TOO_SMALL | The buffer is too small for the operation. |
| STATUS_DEVICE_HARDWARE_ERROR | A hardware error occurred. |
| STATUS_DEVICE_POWERED_OFF | The device is powered off. |
| STATUS_DEVICE_NOT_CONNECTED | The device is not connected. |
| STATUS_DEVICE_PROTOCOL_ERROR | An error occurred at the DP AUX protocol level. The driver can use **DPNativeError** to encode more details about the error. |

## -remarks

Write operations are not supported in Windows 10, version 2004 and should be blocked.

## -see-also

[DXGKARG_DPAUXIOTRANSMISSION](ns-dispmprt-dxgkarg_dpauxiotransmission.md)
