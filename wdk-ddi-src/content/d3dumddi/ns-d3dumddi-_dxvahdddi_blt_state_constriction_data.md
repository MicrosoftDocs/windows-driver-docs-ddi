---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
title: "_DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure describes data that specifies the down-sampling of the output.
old-location: display\dxvahdddi_blt_state_constriction_data.htm
old-project: display
ms.assetid: 5bdb39cc-18b3-4a01-b733-f308273399a1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxvahdddi_blt_state_constriction_data, DXVA2_Structs_4759e9c4-cde3-40d9-8f13-a7437ba73eac.xml, DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, d3dumddi/DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA, DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA
---

# _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure


## -description


The DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure describes data that specifies the down-sampling of the output. If constriction is enabled, the composed target rectangle is down-sampled to the specified size and then scaled back to the target rectangle. 


## -syntax


````
typedef struct _DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA {
  BOOL Enable;
  SIZE Size;
} DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA;
````


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether constriction is enabled. The default value is <b>FALSE</b>, which indicates that constriction is disabled. 


### -field Size

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/dn915850">SIZE</a> structure that specifies the sampling size to which the output image is reduced. <b>Size</b> should be from (1, 1) to (width, height) of the target rectangle. <b>Size</b> should be (0, 0) to represent no constriction. The default value is (1, 1). 


## -remarks



The Direct3D runtime specifies the DXVAHDDDI_BLT_STATE_CONSTRICTION state in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a> function. This is specified only if the driver has previously set the DXVAHDDDI_FEATURE_CAPS_CONSTRICTION value in the <b>FeatureCaps</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. 

Sampling sizes of (0, anything) and (anything, 0) are invalid and the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a> function should return an error if these sampling sizes are supplied.

If the supplied sampling size is larger than the size of the target rectangle, then the driver rounds the sampling size to the size of the target rectangle. 




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn915850">SIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

