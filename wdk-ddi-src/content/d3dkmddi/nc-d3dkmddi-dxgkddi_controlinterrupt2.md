---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT2
title: DXGKDDI_CONTROLINTERRUPT2
author: windows-driver-content
description: The DxgkDdi_ControlInterrupt2 function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt2.htm
old-project: display
ms.assetid: 0C09CAB1-3DFC-4340-8FF2-99CAF7F13156
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdi_ControlInterrupt2
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CONTROLINTERRUPT2 callback



## -description
The <i>DxgkDdi_ControlInterrupt2</i> function enables or disables the given interrupt type on the graphics hardware.



## -prototype

````
DXGKDDI_CONTROLINTERRUPT2 DxgkDdi_ControlInterrupt2;

NTSTATUS APIENTRY* DxgkDdi_ControlInterrupt2(
  _In_ const HANDLE                    hAdapter,
  _In_ const DXGKARG_CONTROLINTERRUPT2 InterruptControl
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the <i>MiniportDeviceContext</i> parameter from a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param InterruptControl [in]

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_controlinterrupt2.md">DXGKARG_CONTROLINTERRUPT2</a>-type value that supplies the interrupt type, as well as the VSYNC state.


## -returns
<i>DxgkDdi_ControlInterrupt2</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The interrupt type was successfully enabled or disabled on the graphics hardware.
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdi_ControlInterrupt2</a> does not support enabling or disabling the specified interrupt type.

 


## -remarks
