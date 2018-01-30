---
UID: NC:dispmprt.DXGKDDI_STOP_DEVICE
title: DXGKDDI_STOP_DEVICE
author: windows-driver-content
description: The DxgkDdiStopDevice function resets a display adapter and frees resources allocated during DxgkDdiStartDevice.
old-location: display\dxgkddistopdevice.htm
old-project: display
ms.assetid: 3c17c7cf-9cfa-421d-a503-88726519fb6c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddistopdevice, DxgkDdiStopDevice callback function [Display Devices], DxgkDdiStopDevice, DXGKDDI_STOP_DEVICE, DXGKDDI_STOP_DEVICE, dispmprt/DxgkDdiStopDevice, DmFunctions_c2d7e95b-beba-488a-b046-98e5daa728b9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiStopDevice
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKDDI_STOP_DEVICE callback


## -description


The <i>DxgkDdiStopDevice</i> function resets a display adapter and frees resources allocated during <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


## -prototype


````
DXGKDDI_STOP_DEVICE DxgkDdiStopDevice;

NTSTATUS DxgkDdiStopDevice(
  _In_ const PVOID MiniportDeviceContext
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


## -returns


<i>DxgkDdiStopDevice</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.



## -remarks


For more information on how this function is used in Plug and Play (PnP) scenarios starting in Windows 8, see <a href="https://msdn.microsoft.com/A95DCFEA-BC1B-4A13-9850-13814725D53E">Plug and Play (PnP) in WDDM 1.2 and later</a>.

The <i>DxgkDdiStopDevice</i> function should be made pageable.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_STOP_DEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

