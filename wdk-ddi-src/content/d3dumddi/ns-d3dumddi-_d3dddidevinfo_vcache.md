---
UID: NS:d3dumddi._D3DDDIDEVINFO_VCACHE
title: "_D3DDDIDEVINFO_VCACHE"
author: windows-driver-content
description: The D3DDDIDEVINFO_VCACHE structure describes the vertex-cache information of a device.
old-location: display\d3dddidevinfo_vcache.htm
tech.root: display
ms.assetid: 06635207-39fd-4ef9-b388-25513f8194fe
ms.date: 05/10/2018
ms.keywords: D3DDDIDEVINFO_VCACHE, D3DDDIDEVINFO_VCACHE structure [Display Devices], D3D_other_Structs_e212d960-07ba-4887-8b31-76ad54a7ae03.xml, _D3DDDIDEVINFO_VCACHE, d3dumddi/D3DDDIDEVINFO_VCACHE, display.d3dddidevinfo_vcache
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIDEVINFO_VCACHE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIDEVINFO_VCACHE
---

# _D3DDDIDEVINFO_VCACHE structure


## -description


The D3DDDIDEVINFO_VCACHE structure describes the vertex-cache information of a device.


## -struct-fields




### -field Pattern

[out] The bit pattern. The driver must specify the bit pattern as a CACH four-character code (FOURCC) value. The driver can use the following MAKEFOURCC macro to specify the FOURCC value as CACH:

```cpp
MAKEFOURCC('C', 'A', 'C', 'H');
```

### -field OptMethod

[out] The method of mesh optimization. The driver can use one of the following values to specify the mesh optimization that it uses.

| **Value** | **Meaning** | 
|:--|:--|
| D3DXMESHOPT_STRIPREORDER (0) | Longest strips optimization | 
| D3DXMESHOPT_VCACHE (1) | Vertex-cache-based optimization | 


### -field CacheSize

[out] The effective size, in entries, that the driver optimizes the vertex cache for. The actual cache size is not required to be the size that is specified in <b>CacheSize</b> because the actual cache size is larger in most situations. The driver specifies an optimized size in <b>CacheSize</b> only if it also specifies D3DXMESHOPT_VCACHE in the <b>OptMethod</b> member.


### -field MagicNumber

[out] The number that should be used as part of a trial-and-error procedure when determining when to restart the strips list. This number can be from 1 to the value that is specified in the <b>CacheSize</b> member. Typically, the best values are near <b>CacheSize</b>/2. The driver specifies a number in <b>MagicNumber</b> only if it also specifies D3DXMESHOPT_VCACHE in the <b>OptMethod</b> member. 


## -remarks



<b>Direct3D runtime version 9.0 and later.</b> The Microsoft Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function to create driver-side resources for the vertex-cache query. In this <b>CreateQuery</b> call, the runtime specifies the D3DDDIQUERYTYPE_VCACHE query type in the <b>QueryType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542958">D3DDDIARG_CREATEQUERY</a> structure. The driver should allocate a D3DDDIDEVINFO_VCACHE structure. The runtime then calls the driver's <a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a> function to process the vertex-cache query. The driver should insert a graphics processing unit (GPU) instruction to write the vertex-cache data to an allocation. To retrieve the vertex-cache information from the driver, the runtime calls the driver's <a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a> function. In this <b>GetQueryData</b> call, the driver should lock the allocation and return the vertex-cache data at the <b>pData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543182">D3DDDIARG_GETQUERYDATA</a> structure that is pointed to by the <i>pData</i> parameter.

<b>Direct3D runtime version 8.1 only.</b> The Direct3D runtime calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a> function to obtain vertex-cache information from the driver. In this <b>GetInfo</b> call, the runtime passes the D3DDDIDEVINFOID_VCACHE flag in the <i>DevInfoID</i> parameter. The driver specifies vertex-cache information in a D3DDDIDEVINFO_VCACHE structure and returns it at the <i>pDevInfoStruct</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542958">D3DDDIARG_CREATEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543182">D3DDDIARG_GETQUERYDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451309">GetInfo</a>



<a href="https://msdn.microsoft.com/64daec14-8e16-4df3-bb0c-27760223b86c">GetQueryData</a>



<a href="https://msdn.microsoft.com/e31b2b6a-3721-472a-8044-6516a8419ad3">IssueQuery</a>
 

 

