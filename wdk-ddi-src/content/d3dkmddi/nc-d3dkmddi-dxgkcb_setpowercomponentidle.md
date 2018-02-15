---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTIDLE
title: DXGKCB_SETPOWERCOMPONENTIDLE
author: windows-driver-content
description: Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed.
old-location: display\dxgkcbsetpowercomponentidle.htm
old-project: display
ms.assetid: 7746d09a-7fb6-4e5d-926c-4ded6830b06d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbsetpowercomponentidle, DxgkCbSetPowerComponentIdle callback function [Display Devices], DxgkCbSetPowerComponentIdle, DXGKCB_SETPOWERCOMPONENTIDLE, DXGKCB_SETPOWERCOMPONENTIDLE, d3dkmddi/DxgkCbSetPowerComponentIdle
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dkmddi.h
apiname:
-	DxgkCbSetPowerComponentIdle
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_SETPOWERCOMPONENTIDLE callback


## -description


Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed. After this function returns, the display miniport driver must not change the component's hardware settings.


## -prototype


````
DXGKCB_SETPOWERCOMPONENTIDLE DxgkCbSetPowerComponentIdle;

VOID APIENTRY CALLBACK* DxgkCbSetPowerComponentIdle(
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



The display miniport driver can call this function for any type of power component, even if the DirectX graphics kernel subsystem manages the idle state of the component.

Each call to this function must be paired with a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a> function.

When this function is called, the active reference count of the component is decreased by 1. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

This function must be called at IRQL &lt;= 		DISPATCH_LEVEL. It can be called at IRQL = 		DISPATCH_LEVEL only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SETPOWERCOMPONENTIDLE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

