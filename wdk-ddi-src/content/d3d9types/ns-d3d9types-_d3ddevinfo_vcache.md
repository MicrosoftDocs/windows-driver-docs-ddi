---
UID: NS:d3d9types._D3DDEVINFO_VCACHE
title: _D3DDEVINFO_VCACHE (d3d9types.h)
description: DirectX 8.1 and later versions only. The D3DDEVINFO_VCACHE structure describes vertex-cache information of a device.
old-location: display\d3ddevinfo_vcache.htm
tech.root: display
ms.assetid: 3c20b757-c27c-446c-a138-066fc57ec1bc
ms.date: 05/10/2018
keywords: ["D3DDEVINFO_VCACHE structure"]
ms.keywords: "*LPD3DDEVINFO_VCACHE, D3DDEVINFO_VCACHE, D3DDEVINFO_VCACHE structure [Display Devices], LPD3DDEVINFO_VCACHE, LPD3DDEVINFO_VCACHE structure pointer [Display Devices], _D3DDEVINFO_VCACHE, d3d9types/D3DDEVINFO_VCACHE, d3d9types/LPD3DDEVINFO_VCACHE, d3dstrct_19dad044-1780-4c89-a518-328f0dfa3a26.xml, display.d3ddevinfo_vcache"
f1_keywords:
 - "d3d9types/D3DDEVINFO_VCACHE"
 - "D3DDEVINFO_VCACHE"
req.header: d3d9types.h
req.include-header: D3d9types.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d9types.h
api_name:
- D3DDEVINFO_VCACHE
targetos: Windows
req.typenames: D3DDEVINFO_VCACHE, *LPD3DDEVINFO_VCACHE
---

# _D3DDEVINFO_VCACHE structure


## -description



   DirectX 8.1 and later versions only.
   

The D3DDEVINFO_VCACHE structure describes vertex-cache information of a device.


## -struct-fields




### -field Pattern

Specifies the bit pattern. The driver must specify the bit pattern as the CACH four-character code (FOURCC) value. The driver can use the MAKEFOURCC macro as follows to specify the FOURCC value as CACH:

```cpp
MAKEFOURCC('C', 'A', 'C', 'H');
```


### -field OptMethod

Specifies the method of mesh optimization. The driver can use one of the following values to specify the mesh optimization that it uses: 

|Value|Meaning|
|--- |--- |
|D3DXMESHOPT_STRIPREORDER (0)|Longest strips optimization|
|D3DXMESHOPT_VCACHE (1)|Vertex-cache based optimization|
 


### -field CacheSize

Specifies the effective size, in entries, for which the driver optimizes the vertex cache. The actual cache size is not required to be the size specified in <b>CacheSize</b> because in most cases the actual cache size turns out to be larger. The driver only specifies an optimized size in <b>CacheSize</b> if it also specifies D3DXMESHOPT_VCACHE in the <b>OptMethod</b> member.


### -field MagicNumber

Specifies the number that should be used as part of a trial-and-error procedure when determining when to restart the strips list. This number can be set from 1 to the value in the <b>CacheSize</b> member. Typically, the best values are near <b>CacheSize</b>/2. 


## -remarks



<b>DirectX 8.1 versions only.</b> The Direct3D runtime calls a driver's <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverstate">D3dGetDriverState</a> function to obtain vertex-cache information from the driver. In this <b>D3dGetDriverState</b> call, the runtime specifies the D3DDEVINFOID_VCACHE flag in the <b>dwFlags</b> member of the DD_GETDRIVERSTATEDATA structure that the runtime passes. The driver specifies vertex-cache information in a D3DDEVINFO_VCACHE structure and returns it at the <b>lpdwStates</b> member of DD_GETDRIVERSTATEDATA.

<b>DirectX 9.0 and later versions only.</b> The Direct3D runtime specifies D3DDP2OP_CREATEQUERY and D3DDP2OP_ISSUEQUERY commands in calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback to create driver-side resources for the query and then to asynchronously query the driver for vertex-cache information. In the call with the D3DDP2OP_CREATEQUERY command, the runtime specifies the D3DQUERYTYPE_VCACHE query type in the <b>QueryType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2createquery">D3DHAL_DP2CREATEQUERY</a> structure. 

When the driver completes a vertex-cache query, the driver sets the total size of the response buffer in the dwErrorOffset member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a> structure and sets the <b>ddrval</b> member of D3DHAL_DRAWPRIMITIVES2DATA to D3D_OK for successful completion. The driver also overwrites the incoming command buffer with the outgoing response buffer. This response buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2responsequery">D3DHAL_DP2RESPONSEQUERY</a> structure that identifies a response for the vertex-cache query. This D3DHAL_DP2RESPONSEQUERY is followed by the vertex-cache data in the D3DDEVINFO_VCACHE structure. 




## -see-also




D3DDP2OP_CREATEQUERY



D3DDP2OP_ISSUEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2createquery">D3DHAL_DP2CREATEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2responsequery">D3DHAL_DP2RESPONSEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverstate">D3dGetDriverState</a>
 

 

