---
UID: NC:d3d10umddi.PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB
title: PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB (d3d10umddi.h)
description: The pfnDisableDeferredStagingResourceDestruction function disables the deferred destruction of staging resources.
old-location: display\pfndisabledeferredstagingresourcedestruction.htm
ms.assetid: f0328782-9b5b-44e6-ac58-7eb72685aa52
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB, PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB callback, d3d10state_functions_2a17cecf-fe42-4058-85d8-524e4ef4d207.xml, d3d10umddi/pfnDisableDeferredStagingResourceDestruction, display.pfndisabledeferredstagingresourcedestruction, pfnDisableDeferredStagingResourceDestruction, pfnDisableDeferredStagingResourceDestruction callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnDisableDeferredStagingResourceDestruction
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_DISABLE_DEFERRED_STAGING_RESOURCE_DESTRUCTION_CB callback function


## -description


The <b>pfnDisableDeferredStagingResourceDestruction</b> function disables the deferred destruction of staging resources.


## -parameters




### -param Arg1


*hRuntimeDevice* [in]

A handle to a context for the core Microsoft Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



By default, the Direct3D runtime defers the destruction of staging resources, until a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy">ResourceIsStagingBusy</a> function indicates that the graphics pipeline no longer uses the resources. The runtime defers the destruction of staging resources because the destruction of a staging resource, while still in use, might cause the processor to block until the resource is no longer used. 

If the user-mode display driver can ensure that this type of block can be avoided, the driver can call <b>pfnDisableDeferredStagingResourceDestruction</b> to disable the deferred destruction behavior.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceisstagingbusy">ResourceIsStagingBusy</a>
 

 

