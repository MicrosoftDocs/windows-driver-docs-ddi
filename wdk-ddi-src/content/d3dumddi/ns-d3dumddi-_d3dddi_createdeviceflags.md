---
UID: NS:d3dumddi._D3DDDI_CREATEDEVICEFLAGS
title: _D3DDDI_CREATEDEVICEFLAGS (d3dumddi.h)
description: The D3DDDI_CREATEDEVICEFLAGS structure describes how to create a device.
old-location: display\d3dddi_createdeviceflags.htm
tech.root: display
ms.assetid: f9415dc9-352a-4e93-a0c1-2519c8c89762
ms.date: 05/10/2018
keywords: ["_D3DDDI_CREATEDEVICEFLAGS structure"]
ms.keywords: D3DDDI_CREATEDEVICEFLAGS, D3DDDI_CREATEDEVICEFLAGS structure [Display Devices], D3D_other_Structs_45151acf-e91a-454b-be32-b7b7aaa619e9.xml, _D3DDDI_CREATEDEVICEFLAGS, d3dumddi/D3DDDI_CREATEDEVICEFLAGS, display.d3dddi_createdeviceflags
f1_keywords:
 - "d3dumddi/D3DDDI_CREATEDEVICEFLAGS"
 - "D3DDDI_CREATEDEVICEFLAGS"
req.header: d3dumddi.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
- d3dumddi.h
api_name:
- D3DDDI_CREATEDEVICEFLAGS
targetos: Windows
req.typenames: D3DDDI_CREATEDEVICEFLAGS
---

# _D3DDDI_CREATEDEVICEFLAGS structure


## -description


The D3DDDI_CREATEDEVICEFLAGS structure describes how to create a device.


## -struct-fields




### -field AllowMultithreading

A UINT value that specifies whether the user-mode display driver can run multiple threads simultaneously when it processes calls to its functions from the Microsoft Direct3D runtime. For situations where the driver must disable multi-threading even when <b>AllowMultithreading</b> is set, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supporting-multiple-processors">Supporting Multiple Processors</a>. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field AllowFlipBatching

A UINT value that specifies whether the user-mode display driver can queue flip operation requests so the driver can process them later on another thread. This flag applies only to when a driver implements its own threading. In this situation, the driver is not required to immediately call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_presentcb">pfnPresentCb</a> function when its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a> function is called. 

The Direct3D runtime enforces a queued present limit (currently set to 1) to ensure that frame latency stays at a reasonable level. If an application initiates a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_present">Present</a> function while another present operation is queued, the current version of the runtime will flush the queued present. However, drivers should not rely on this behavior because the queued present limit might change in future versions of the runtime.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFD) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_CREATEDEVICEFLAGS that can hold one 32-bit value that identifies how to create the device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>
 

 

