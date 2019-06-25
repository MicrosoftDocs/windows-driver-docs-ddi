---
UID: NS:dxgiddi._DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT
title: _DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT (dxgiddi.h)
description: Used in a call to the pfnCheckPresentDurationSupport(DXGI) function to check details on hardware device support for seamlessly switching to a new monitor refresh rate.
old-location: display\dxgi_ddi_arg_checkpresentdurationsupport.htm
tech.root: display
ms.assetid: FE12CFAB-3936-4453-88B5-A4CF0CA51E1A
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT, DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT structure [Display Devices], _DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT, display.dxgi_ddi_arg_checkpresentdurationsupport, dxgiddi/DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT
ms.topic: struct
req.header: dxgiddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
- Dxgiddi.h
api_name:
- DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT
---

# _DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT structure


## -description


Used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-_dxgi_ddi_arg_checkpresentdurationsupport">pfnCheckPresentDurationSupport(DXGI)</a> function to check details on hardware device support for seamlessly switching to a new monitor refresh rate.


## -struct-fields




### -field hDevice

A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field VidPnSourceId

The zero-based video present network (VidPN) source identification number of the input for which the hardware support is queried.


### -field DesiredPresentDuration

The desired duration of a single present operation, in units of 100 nanoseconds.


### -field ClosestSmallerDuration

The smallest supported desired duration of a single present operation on the given VidPN source, in units of 100 nanoseconds. The value must be ≤ <b>DesiredPresentDuration</b>.

See Remarks for more limitations on this value.


### -field ClosestLargerDuration

[out] The largest supported desired duration of a single present operation on the given VidPN source, in units of 100 nanoseconds. The value must be ≥ <b>DesiredPresentDuration</b>.

See Remarks for more limitations on this value.


## -remarks



Either  <b>ClosestSmallerDuration</b> or <b>ClosestLargerDuration</b> can be zero. However, if both  are zero, the device cannot seamlessly switch to a new refresh rate.

If both <b>ClosestSmallerDuration</b> and <b>ClosestLargerDuration</b> have the same value as <b>DesiredPresentDuration</b>, the device can precisely match <b>DesiredPresentDuration</b>.

The difference between <b>DesiredPresentDuration</b> and <b>ClosestSmallerDuration</b> (or <b>ClosestLargerDuration</b>) represents the driver’s knowledge of the device capabilities, but there will be additional error during execution. The final accuracy of the device when using per-present durations should typically be the same as the accuracy using  existing presentation modes.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dxgiddi/ns-dxgiddi-_dxgi_ddi_arg_checkpresentdurationsupport">pfnCheckPresentDurationSupport(DXGI)</a>
 

 

