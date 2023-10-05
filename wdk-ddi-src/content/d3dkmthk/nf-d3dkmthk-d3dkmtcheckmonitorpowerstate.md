---
UID: NF:d3dkmthk.D3DKMTCheckMonitorPowerState
title: D3DKMTCheckMonitorPowerState function (d3dkmthk.h)
description: The D3DKMTCheckMonitorPowerState function verifies the power state of a monitor. The function returns STATUS_SUCCESS on successful verification.
old-location: display\d3dkmtcheckmonitorpowerstate.htm
ms.date: 02/23/2022
keywords: ["D3DKMTCheckMonitorPowerState function"]
ms.keywords: D3DKMTCheckMonitorPowerState, D3DKMTCheckMonitorPowerState callback function [Display Devices], OpenGL_Functions_d05a2b63-fe81-45f0-908d-94043416b1d0.xml, PFND3DKMT_CHECKMONITORPOWERSTATE, PFND3DKMT_CHECKMONITORPOWERSTATE callback, d3dkmthk/D3DKMTCheckMonitorPowerState, display.d3dkmtcheckmonitorpowerstate
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTCheckMonitorPowerState
 - d3dkmthk/D3DKMTCheckMonitorPowerState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTCheckMonitorPowerState
---

# D3DKMTCheckMonitorPowerState function

## -description

The **D3DKMTCheckMonitorPowerState** function verifies the power state of a monitor.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_CHECKMONITORPOWERSTATE](ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate.md) structure that describes the connection to the monitor for which to check the power state.

## -returns

**D3DKMTCheckMonitorPowerState** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The power state of the monitor was successfully verified. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_CHECKMONITORPOWERSTATE](ns-d3dkmthk-_d3dkmt_checkmonitorpowerstate.md)
