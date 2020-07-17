---
UID: NS:d3d10umddi.D3D10DDIARG_OPENADAPTER
title: D3D10DDIARG_OPENADAPTER (d3d10umddi.h)
description: The D3D10DDIARG_OPENADAPTER structure describes the graphics adapter object.
old-location: display\d3d10ddiarg_openadapter.htm
ms.assetid: ac1bf173-8c18-4bb4-9a85-79b59f27ee55
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_OPENADAPTER structure"]
ms.keywords: D3D10DDIARG_OPENADAPTER, D3D10DDIARG_OPENADAPTER structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3dd9df89-1d5e-4eab-bbe5-c6585543c093.xml, d3d10umddi/D3D10DDIARG_OPENADAPTER, display.d3d10ddiarg_openadapter
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_OPENADAPTER"
 - "D3D10DDIARG_OPENADAPTER"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_OPENADAPTER
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_OPENADAPTER
---

# D3D10DDIARG_OPENADAPTER structure


## -description


The D3D10DDIARG_OPENADAPTER structure describes the graphics adapter object.


## -struct-fields




### -field hRTAdapter

[in] A handle to the graphics adapter object that specifies the handle that the driver should use to query for graphics adapter capabilities when the driver calls the Microsoft Direct3D runtime-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> callback function. 


### -field hAdapter

[out] A handle to the graphics adapter object that specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object. The driver generates a unique handle and passes it back to the Direct3D runtime. 


### -field Interface

[in] The Direct3D interface version. The high 16 bits store the major release number (such as 10, 11, and so on); the low 16 bits store the minor release number (such as 0, 1, 2, and so on). The minor release number will be increased when a change to the interface is released.


### -field Version

[in] A number that the driver can use to identify when the Direct3D runtime was built. The high 16 bits represent the build number; the low 16 bits represent the revision number. 

The driver is required only to monitor the high 16 bits. The driver should ensure that the runtime build version that is passed in is greater than or equal to the current build version of the driver. The driver should return a failure from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openadapter">OpenAdapter10</a> function if the passed in build version is incompatible. 


### -field pAdapterCallbacks

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a> structure that contains the Direct3D runtime-supplied <b>pfnQueryAdapterInfoCb</b> callback function that the driver can use.


### -field pAdapterFuncs

[out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_adapterfuncs">D3D10DDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.


### -field pAdapterFuncs_2

Supported in Windows 7 and later versions.

[out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_2ddi_adapterfuncs">D3D10_2DDI_ADAPTERFUNCS</a> structure that contains a table of user-mode display driver adapter-specific functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver about operations that are specific to the graphics adapter.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_adapterfuncs">D3D10DDI_ADAPTERFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_2ddi_adapterfuncs">D3D10_2DDI_ADAPTERFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_openadapter">OpenAdapter10</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a>
 

 

