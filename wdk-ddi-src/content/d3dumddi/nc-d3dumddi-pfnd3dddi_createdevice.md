---
UID: NC:d3dumddi.PFND3DDDI_CREATEDEVICE
title: PFND3DDDI_CREATEDEVICE (d3dumddi.h)
description: The CreateDevice function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice.htm
tech.root: display
ms.assetid: ce35bdac-af90-471f-af93-0e665be6c7f6
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATEDEVICE callback function"]
ms.keywords: CreateDevice, CreateDevice callback function [Display Devices], PFND3DDDI_CREATEDEVICE, PFND3DDDI_CREATEDEVICE callback, UserModeDisplayDriver_Functions_4603a980-54aa-4d90-859a-d84c2afe5f03.xml, d3dumddi/CreateDevice, display.createdevice
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/CreateDevice"
 - "CreateDevice"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateDevice
product:
 - Windows
---

# PFND3DDDI_CREATEDEVICE callback function

## -description

The <b>CreateDevice</b> function creates a graphics context that is referenced in subsequent calls.

## -parameters

### -param hAdapter

A handle that identifies the graphics adapter.

### -param Arg2

*pCreateData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.

## -returns

<b>CreateDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The graphics context is successfully created. | 
| **E_OUTOFMEMORY** | [CreateDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice)  could not allocate the memory that was required for it to complete. |

## -remarks

A display device is a graphics context that is used to hold a collection of rendering state. Multiple devices can be created by the same process on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.

Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.

When the Direct3D runtime calls <b>CreateDevice</b> to create a device, the runtime does not create a default graphics processing unit (GPU) context thread of execution for the device. The driver must explicitly call the <a href="https://docs.microsoft.com/previous-versions/ff568895(v=vs.85)">pfnCreateContextCb</a> function to create one or more contexts as required.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adapterfuncs">D3DDDI_ADAPTERFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_destroydevice">DestroyDevice</a>

