---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT
title: DXGKDDI_CONTROLINTERRUPT (d3dkmddi.h)
description: The DxgkDdiControlInterrupt function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt.htm
ms.assetid: d6bef242-bafc-4d9e-a729-d62ccdbd2667
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CONTROLINTERRUPT, DXGKDDI_CONTROLINTERRUPT callback, DmFunctions_a124d234-9609-4f21-a1f5-c1f4cfa65d9c.xml, DxgkDdiControlInterrupt, DxgkDdiControlInterrupt callback function [Display Devices], d3dkmddi/DxgkDdiControlInterrupt, display.dxgkddicontrolinterrupt
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkDdiControlInterrupt"
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
- DxgkDdiControlInterrupt
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_CONTROLINTERRUPT callback function


## -description


The <i>DxgkDdiControlInterrupt</i> function enables or disables the given interrupt type on the graphics hardware.


## -parameters




### -param hAdapter [in]

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the <i>MiniportDeviceContext</i> parameter from a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param InterruptType [in]

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a>-type value that supplies the interrupt type.


### -param EnableInterrupt



[in] A Boolean value that indicates whether <i>DxgkDdiControlInterrupt</i> enables or disables the specified interrupt type. <b>TRUE</b> indicates that it enables and <b>FALSE</b> indicates that it disables.


## -returns



<i>DxgkDdiControlInterrupt</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The interrupt type was successfully enabled or disabled on the graphics hardware.|
|STATUS_NOT_IMPLEMENTED|*DxgkDdiControlInterrupt* does not support enabling or disabling the specified interrupt type.|


## -remarks



The display miniport driver's <i>DxgkDdiControlInterrupt</i> function can enable or disable the specified interrupt type. However, <i>DxgkDdiControlInterrupt</i> is not required to disable the interrupt type if the driver requires the interrupt type for an internal purpose. A call to <i>DxgkDdiControlInterrupt</i> to enable the specified interrupt type indicates that the operating system requires that the driver call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a> function to report when the interrupt type is triggered on the graphics hardware.

Currently, the Microsoft DirectX graphics kernel subsystem specifies only the DXGK_INTERRUPT_CRTC_VSYNC interrupt type in the <i>InterruptType</i> parameter. A call to <i>DxgkDdiControlInterrupt</i> to enable the DXGK_INTERRUPT_CRTC_VSYNC interrupt type indicates for the driver to control vertical retrace interrupt. During every vertical retrace period and immediately after the primary surface address specified in the DAC register is latched and scanned out, the interrupt should be triggered and reported. 

The driver must return STATUS_NOT_IMPLEMENTED if an interrupt type other than DXGK_INTERRUPT_CRTC_VSYNC is supplied.

<i>DxgkDdiControlInterrupt</i> should be made pageable.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

