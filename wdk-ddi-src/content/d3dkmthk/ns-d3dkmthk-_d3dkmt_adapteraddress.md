---
UID: NS:d3dkmthk._D3DKMT_ADAPTERADDRESS
title: _D3DKMT_ADAPTERADDRESS (d3dkmthk.h)
description: The D3DKMT_ADAPTERADDRESS structure describes the physical location of the graphics adapter.
old-location: display\d3dkmt_adapteraddress.htm
ms.assetid: 70f45ca2-4be6-4e74-b2e8-55ef7a43192f
ms.date: 05/10/2018
ms.keywords: D3DKMT_ADAPTERADDRESS, D3DKMT_ADAPTERADDRESS structure [Display Devices], OpenGL_Structs_98b1caf8-46c4-4f78-896c-031e8f3f61d0.xml, _D3DKMT_ADAPTERADDRESS, d3dkmthk/D3DKMT_ADAPTERADDRESS, display.d3dkmt_adapteraddress
f1_keywords:
 - "d3dkmthk/D3DKMT_ADAPTERADDRESS"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMT_ADAPTERADDRESS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_ADAPTERADDRESS
---

# _D3DKMT_ADAPTERADDRESS structure


## -description


The D3DKMT_ADAPTERADDRESS structure describes the physical location of the graphics adapter. 


## -struct-fields




### -field BusNumber

[out] The number of the bus that the graphics adapter's physical device is located on.


### -field DeviceNumber

[out] The index of the graphics adapter's physical device on the bus.


### -field FunctionNumber

[out] The function number of the graphics adapter on the physical device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>
 

 

