---
UID: NC:dispmprt.DXGKDDI_MIRACAST_QUERY_CAPS
title: DXGKDDI_MIRACAST_QUERY_CAPS (dispmprt.h)
description: Queries the Miracast capabilities of the current display adapter.
old-location: display\dxgkddimiracastquerycaps.htm
tech.root: display
ms.assetid: C10CAA33-C407-4183-9090-B9D78B07CD12
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MIRACAST_QUERY_CAPS, DXGKDDI_MIRACAST_QUERY_CAPS callback, DxgkDdiMiracastQueryCaps, DxgkDdiMiracastQueryCaps callback function [Display Devices], display.dxgkddimiracastquerycaps, dispmprt/DxgkDdiMiracastQueryCaps
f1_keywords:
 - "dispmprt/DxgkDdiMiracastQueryCaps"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Dispmprt.h
api_name:
- DxgkDdiMiracastQueryCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_MIRACAST_QUERY_CAPS callback function


## -description


Queries the Miracast capabilities of the current display adapter. The operating system  calls this function only when the display adapter is first started and then stores the capabilities that are returned.<div class="alert"><b>Note</b>  The capabilities of the display adapter must not change while it is connected.</div>
<div> </div>



## -parameters




### -param DriverContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param MiracastCapsSize [in]

The size, supplied by the operating system, of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a> structure pointed to by the <i>MiracastCaps</i> parameter.

The driver should check this value before it fills the structure.


### -param *MiracastCaps [out]

A pointer to an operating system-provided buffer that holds a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a> structure that the driver fills with Miracast device capabilities.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.




## -remarks



<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
The operating system guarantees that this function follows the third-level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-third-level">Threading and Synchronization Third Level</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_miracast_caps">DXGK_MIRACAST_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>
 

 

