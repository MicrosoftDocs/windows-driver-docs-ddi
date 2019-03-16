---
UID: NF:d3dkmthk.D3DKMTFreeGpuVirtualAddress
title: D3DKMTFreeGpuVirtualAddress function (d3dkmthk.h)
description: D3DKMTFreeGpuVirtualAddress releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.
old-location: display\d3dkmtfreegpuvirtualaddress.htm
ms.assetid: E076E9E6-FA7E-4F46-88B4-D3971E62DE1A
ms.date: 05/10/2018
ms.keywords: D3DKMTFreeGpuVirtualAddress, D3DKMTFreeGpuVirtualAddress function [Display Devices], d3dkmthk/D3DKMTFreeGpuVirtualAddress, display.d3dkmtfreegpuvirtualaddress
ms.topic: function
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
- D3DKMTFreeGpuVirtualAddress
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTFreeGpuVirtualAddress function

## -description

<b>D3DKMTFreeGpuVirtualAddress</b> releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped. 

## -parameters

### -param D3DKMT_FREEGPUVIRTUALADDRESS

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906795">D3DKMT_FREEGPUVIRTUALADDRESS</a> structure that describes the operation.


## -returns

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The device context was successfully created.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -remarks

The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="https://msdn.microsoft.com/6CE8112F-1DDA-4A8B-8D3D-40DC3737976A">MapGpuVirtualAddress</a> and <a href="https://msdn.microsoft.com/3390A01D-BD4B-4399-AA3E-91BB32264A13">UpdateGpuVirtualAddress</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906795">D3DKMT_FREEGPUVIRTUALADDRESS</a>



<a href="https://msdn.microsoft.com/6CE8112F-1DDA-4A8B-8D3D-40DC3737976A">MapGpuVirtualAddress</a>



<a href="https://msdn.microsoft.com/3390A01D-BD4B-4399-AA3E-91BB32264A13">UpdateGpuVirtualAddress</a>
 

 

