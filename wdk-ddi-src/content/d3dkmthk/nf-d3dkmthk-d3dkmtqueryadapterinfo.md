---
UID: NF:d3dkmthk.D3DKMTQueryAdapterInfo
title: D3DKMTQueryAdapterInfo function (d3dkmthk.h)
description: The D3DKMTQueryAdapterInfo function retrieves graphics adapter information.
old-location: display\d3dkmtqueryadapterinfo.htm
ms.assetid: fa67207d-cf83-42a5-969b-29379f99883f
ms.date: 11/21/2018
ms.keywords: D3DKMTQueryAdapterInfo, D3DKMTQueryAdapterInfo function [Display Devices], OpenGL_Functions_124c9878-58d2-414b-8b3c-392748ca5361.xml, d3dkmthk/D3DKMTQueryAdapterInfo, display.d3dkmtqueryadapterinfo
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTQueryAdapterInfo"
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
- D3DKMTQueryAdapterInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTQueryAdapterInfo function

## -description
The <b>D3DKMTQueryAdapterInfo</b> function retrieves various adapter information from an adapter handle.

## -parameters

### -param D3DKMT_QUERYADAPTERINFO
*\_In\_* *[D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)* * *Arg1*

See documentation of structure type for more details.

## -returns
Returns NTSTATUS.

<b>D3DKMTQueryAdapterInfo</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | Adapter information was successfully retrieved. | 
| **STATUS_DEVICE_REMOVED** | The adapter was stopped. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTQueryAdapterInfo](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo)  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -see-also
- [D3DKMT_QUERYADAPTERINFO](ns-d3dkmthk-_d3dkmt_queryadapterinfo.md)
- [PFND3DKMT_QUERYADAPTERINFO](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)



 

