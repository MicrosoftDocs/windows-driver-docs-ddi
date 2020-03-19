---
UID: NF:d3dkmthk.D3DKMTUnregisterTrimNotification
title: D3DKMTUnregisterTrimNotification function (d3dkmthk.h)
description: D3DKMTUnregisterTrimNotification is used to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmtunregistertrimnotification.htm
ms.assetid: C90A5200-F6AF-4B7B-BB66-D76D4C3AA8EE
ms.date: 05/10/2018
keywords: ["D3DKMTUnregisterTrimNotification function"]
ms.keywords: D3DKMTUnregisterTrimNotification, D3DKMTUnregisterTrimNotification function [Display Devices], d3dkmthk/D3DKMTUnregisterTrimNotification, display.d3dkmtunregistertrimnotification
f1_keywords:
 - "d3dkmthk/D3DKMTUnregisterTrimNotification"
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
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTUnregisterTrimNotification
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTUnregisterTrimNotification function

## -description

<b>D3DKMTUnregisterTrimNotification</b> is used to remove a callback registration for a kernel mode device receiving notifications from a graphics framework (such as OpenGL).
<div class="alert"><b>Note</b>  The callback must be unregistered prior to unloading the module that contains the callback function and destroying the registered kernel mode device.</div><div> </div>

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_unregistertrimnotification">D3DKMT_UNREGISTERTRIMNOTIFICATION</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtregistertrimnotification">D3DKMTRegisterTrimNotification</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_unregistertrimnotification">D3DKMT_UNREGISTERTRIMNOTIFICATION</a>
