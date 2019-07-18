---
UID: NC:d3dkmddi.DXGKDDI_SETTARGETCONTENTTYPE
title: DXGKDDI_SETTARGETCONTENTTYPE (d3dkmddi.h)
description: Passes the content type for which the driver should optimize on the specified target.
old-location: display\dxgkddi_settargetcontenttype.htm
ms.assetid: 7639BF7B-6219-4490-953F-80E76CDFBAAA
ms.date: 05/10/2018
ms.keywords: DXGKDDI_SETTARGETCONTENTTYPE, DXGKDDI_SETTARGETCONTENTTYPE callback, DXGKDDI_SETTARGETCONTENTTYPE callback function [Display Devices], d3dkmddi/DXGKDDI_SETTARGETCONTENTTYPE, display.dxgkddi_settargetcontenttype
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKDDI_SETTARGETCONTENTTYPE"
req.header: d3dkmddi.h
req.include-header: 
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
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DXGKDDI_SETTARGETCONTENTTYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_SETTARGETCONTENTTYPE callback function


## -description


Passes the content type for which the driver should optimize on the specified target.  <div class="alert"><b>Note</b>  This is functionally equivalent to the DxgkDdi_UpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_VIDPN_PRESENT_PATH_CONTENT field is changed.</div>
<div> </div>



## -parameters




### -param hAdapter [in]

A handle that identifies the adapter.


### -param pSetTargetContentTypeArg [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_settargetcontenttype">DXGKARG_SETTARGETCONTENTTYPE</a> structure that provides the target to be modified and the new type of content being displayed on it.


## -returns



If this routine succeeds, it returns STATUS_SUCCESS. 




## -remarks



This is an optional DDI, so the function pointer in DRIVER_INITIALIZATION_DATA should be set to null if the DDI is not implemented for every adapter supported by the driver.
This function is always called at PASSIVE level so the supporting code should be made pageable.




