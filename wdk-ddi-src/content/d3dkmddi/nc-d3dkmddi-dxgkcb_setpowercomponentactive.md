---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTACTIVE
title: DXGKCB_SETPOWERCOMPONENTACTIVE
author: windows-driver-content
description: Called by the display miniport driver to access a power component.
old-location: display\dxgkcbsetpowercomponentactive.htm
old-project: display
ms.assetid: 12008d80-8bcb-4289-97ea-d3325731a95f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTACTIVE, DxgkCbSetPowerComponentActive, DxgkCbSetPowerComponentActive callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentActive, display.dxgkcbsetpowercomponentactive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkCbSetPowerComponentActive
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_SETPOWERCOMPONENTACTIVE callback


## -description


Called by the display miniport driver to access a power component. After this function returns, the display miniport driver can change the component's hardware settings.


## -prototype


````
DXGKCB_SETPOWERCOMPONENTACTIVE DxgkCbSetPowerComponentActive;

VOID APIENTRY CALLBACK* DxgkCbSetPowerComponentActive(
  _In_ const HANDLE hAdapter,
             UINT   ComponentIndex
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param ComponentIndex

The power component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -returns



This callback function does not return a value.




## -remarks



Each call to this function must be paired with a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentidle.md">DxgkCbSetPowerComponentIdle</a> function to indicate that the component hardware is no longer required.

When this function is called, the active reference count of the component is increased by 1. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

While calling this function, the display miniport driver might receive a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a> function on another execution thread.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentidle.md">DxgkCbSetPowerComponentIdle</a>



<a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SETPOWERCOMPONENTACTIVE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

