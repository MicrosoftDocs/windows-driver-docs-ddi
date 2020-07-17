---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
title: _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA (d3dumddi.h)
description: The DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure describes data that specifies the down-sampling of the output.
old-location: display\dxvahdddi_blt_state_constriction_data.htm
tech.root: display
ms.assetid: 5bdb39cc-18b3-4a01-b733-f308273399a1
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure"]
ms.keywords: DXVA2_Structs_4759e9c4-cde3-40d9-8f13-a7437ba73eac.xml, DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure [Display Devices], _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, display.dxvahdddi_blt_state_constriction_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA"
 - "DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
---

# _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure describes data that specifies the down-sampling of the output. If constriction is enabled, the composed target rectangle is down-sampled to the specified size and then scaled back to the target rectangle. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether constriction is enabled. The default value is <b>FALSE</b>, which indicates that constriction is disabled. 


### -field Size

[in] A <a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-smbserver-size">SIZE</a> structure that specifies the sampling size to which the output image is reduced. <b>Size</b> should be from (1, 1) to (width, height) of the target rectangle. <b>Size</b> should be (0, 0) to represent no constriction. The default value is (1, 1). 


## -remarks



The Direct3D runtime specifies the DXVAHDDDI_BLT_STATE_CONSTRICTION state in the <b>State</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a> function. This is specified only if the driver has previously set the DXVAHDDDI_FEATURE_CAPS_CONSTRICTION value in the <b>FeatureCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. 

Sampling sizes of (0, anything) and (anything, 0) are invalid and the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a> function should return an error if these sampling sizes are supplied.

If the supplied sampling size is larger than the size of the target rectangle, then the driver rounds the sampling size to the size of the target rectangle. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-smbserver-size">SIZE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate">SetVideoProcessBltState</a>
 

 

