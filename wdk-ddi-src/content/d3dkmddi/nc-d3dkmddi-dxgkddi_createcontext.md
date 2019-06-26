---
UID: NC:d3dkmddi.DXGKDDI_CREATECONTEXT
title: DXGKDDI_CREATECONTEXT (d3dkmddi.h)
description: The DxgkDdiCreateContext function creates a graphics processing unit (GPU) context.
old-location: display\dxgkddicreatecontext.htm
ms.assetid: aea21a36-f3d5-4541-bd2d-aa026668c562
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CREATECONTEXT, DXGKDDI_CREATECONTEXT callback, DmFunctions_b1519a67-52c0-4432-9059-ef1c98f075b6.xml, DxgkDdiCreateContext, DxgkDdiCreateContext callback function [Display Devices], d3dkmddi/DxgkDdiCreateContext, display.dxgkddicreatecontext
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkDdiCreateContext
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_CREATECONTEXT callback function


## -description


The <i>DxgkDdiCreateContext</i> function creates a graphics processing unit (GPU) context. 


## -parameters




### -param hDevice [in]

[in] A handle to the graphics context device that the new context is created on. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a> structure. 


### -param pCreateContext [in, out]

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a> structure that contains information about creating the context.


## -returns



<i>DxgkDdiCreateContext</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|DxgkDdiCreateContext successfully created the context.|
|STATUS_NO_MEMORY|DxgkDdiCreateContext could not allocate memory that was required for it to complete.|
|STATUS_GRAPHICS_DRIVER_MISMATCH|The display miniport driver is not compatible with the user-mode display driver that initiated the call to DxgkDdiCreateContext.|



## -remarks



A driver uses a GPU context to hold a collection of rendering state. 

A single process can create multiple contexts on a given device. 

The driver must support an arbitrary number of contexts. The only valid reason why a driver could not create a context is if system memory runs out. 

Typically, each context can reference any resource that was previously created for the device that owns that context. 

<i>DxgkDdiCreateContext</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createdevice">DXGKARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>
 

 

