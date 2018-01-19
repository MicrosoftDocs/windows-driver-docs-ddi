---
UID: NC:d3dkmddi.DXGKDDI_CREATEDEVICE
title: DXGKDDI_CREATEDEVICE
author: windows-driver-content
description: The DxgkDdiCreateDevice function creates a graphics context device that is subsequently used in calls to the display miniport driver's device-specific functions.
old-location: display\dxgkddicreatedevice.htm
old-project: display
ms.assetid: a7027735-0ec4-4fad-81fb-1c3aca4ebf2d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiCreateDevice
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

# DXGKDDI_CREATEDEVICE callback



## -description
The <i>DxgkDdiCreateDevice</i> function creates a graphics context device that is subsequently used in calls to the display miniport driver's device-specific functions.



## -prototype

````
DXGKDDI_CREATEDEVICE DxgkDdiCreateDevice;

NTSTATUS APIENTRY DxgkDdiCreateDevice(
  _In_    const HANDLE               hAdapter,
  _Inout_       DXGKARG_CREATEDEVICE *pCreateDevice
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCreateDevice [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure that describes the graphics context device.


## -returns
<i>DxgkDdiCreateDevice</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiCreateDevice</i> successfully created the graphics context device.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiCreateDevice</i> could not allocate memory that was required for it to complete.

 


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiCreateDevice</i> function to create a graphics context device that the graphics subsystem subsequently passes in calls to the display miniport driver. The driver uses a device to hold a collection of rendering state. The graphics subsystem can create multiple devices in the same process on a given graphics processing unit (GPU) adapter. 

Generally, devices are independent of each other; in other words, resources that are created in one device cannot be referenced or accessed by resources that are created in another device. However, cross-process resources are an exception to this rule. 

<i>DxgkDdiCreateDevice</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CREATEDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

