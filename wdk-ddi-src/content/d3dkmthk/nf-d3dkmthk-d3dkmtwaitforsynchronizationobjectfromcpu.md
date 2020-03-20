---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromCpu
title: D3DKMTWaitForSynchronizationObjectFromCpu function (d3dkmthk.h)
description: D3DKMTWaitForSynchronizationObjectFromCpu waits for a monitored fence to reach a certain value.
old-location: display\d3dkmtwaitforsynchronizationobjectfromcpu.htm
ms.assetid: C65880F7-DFCA-4DF9-ABF1-95A82D1D43ED
ms.date: 05/10/2018
keywords: ["D3DKMTWaitForSynchronizationObjectFromCpu function"]
ms.keywords: D3DKMTWaitForSynchronizationObjectFromCpu, D3DKMTWaitForSynchronizationObjectFromCpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromCpu, display.d3dkmtwaitforsynchronizationobjectfromcpu
f1_keywords:
 - "d3dkmthk/D3DKMTWaitForSynchronizationObjectFromCpu"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTWaitForSynchronizationObjectFromCpu
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTWaitForSynchronizationObjectFromCpu function

## -description

<b>D3DKMTWaitForSynchronizationObjectFromCpu</b> waits for a monitored fence to reach a certain value.

## -parameters

### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU</a>
