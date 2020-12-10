---
UID: NF:d3dkmthk.D3DKMTPollDisplayChildren
title: D3DKMTPollDisplayChildren function (d3dkmthk.h)
description: The D3DKMTPollDisplayChildren function queries for connectivity status of all child devices of the given adapter.
old-location: display\d3dkmtpolldisplaychildren.htm
ms.date: 05/10/2018
keywords: ["D3DKMTPollDisplayChildren function"]
ms.keywords: D3DKMTPollDisplayChildren, D3DKMTPollDisplayChildren function [Display Devices], OpenGL_Functions_dc39afab-758a-423a-9058-9d9ec091d4b2.xml, d3dkmthk/D3DKMTPollDisplayChildren, display.d3dkmtpolldisplaychildren
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
 - D3DKMTPollDisplayChildren
 - d3dkmthk/D3DKMTPollDisplayChildren
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTPollDisplayChildren
---

# D3DKMTPollDisplayChildren function


## -description

The <b>D3DKMTPollDisplayChildren</b> function queries for connectivity status of all child devices of the given adapter.

## -parameters

### -param D3DKMT_POLLDISPLAYCHILDREN

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a> structure that describes the parameters for querying for connectivity status of the adapter's child devices.

## -returns

<b>D3DKMTPollDisplayChildren</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|Connectivity status was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped.|

This function might also return other NTSTATUS values.

## -remarks

The OpenGL installable client driver (ICD) calls <b>D3DKMTPollDisplayChildren</b> to query for connectivity status of all of the adapter's child devices. The ICD sets the <b>NonDestructiveOnly</b> member of <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a> to indicate whether <b>D3DKMTPollDisplayChildren</b> should be destructive (that is, cause visual artifacts). For typical polling, the ICD should set <b>NonDestructiveOnly</b> to <b>TRUE</b> to prevent the screen from flickering.

New child devices are enumerated to the Plug and Play (PnP) manager when PnP detects them. The devices are then listed in the device manager. If PnP determines that a child device was removed, the device is reported as a surprise removal.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a>
