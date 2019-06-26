---
UID: NC:d3d10umddi.PFND3D10DDI_IA_SETTOPOLOGY
title: PFND3D10DDI_IA_SETTOPOLOGY (d3d10umddi.h)
description: The IaSetTopology function sets the primitive topology to enable drawing for the input assember.
old-location: display\iasettopology.htm
ms.assetid: c2ee9c8b-7e33-4fc9-9bd3-2b2984e94390
ms.date: 05/10/2018
ms.keywords: IaSetTopology, IaSetTopology callback function [Display Devices], PFND3D10DDI_IA_SETTOPOLOGY, PFND3D10DDI_IA_SETTOPOLOGY callback, UserModeDisplayDriverDx10_Functions_9c7ceca5-4745-4550-832d-d85cdcfecf81.xml, d3d10umddi/IaSetTopology, display.iasettopology
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
- IaSetTopology
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_IA_SETTOPOLOGY callback function


## -description


The <i>IaSetTopology</i> function sets the primitive topology to enable drawing for the input assember.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*PrimitiveTopology* [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10_ddi_primitive_topology">D3D10_DDI_PRIMITIVE_TOPOLOGY</a>-typed value that indicates the primitive topology to set. 




## -returns



None

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>IaSetTopology</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10_ddi_primitive_topology">D3D10_DDI_PRIMITIVE_TOPOLOGY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 

