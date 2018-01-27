---
UID: NC:dispmprt.DXGKDDI_ADD_DEVICE
title: DXGKDDI_ADD_DEVICE
author: windows-driver-content
description: The DxgkDdiAddDevice function creates a context block for a display adapter and returns a handle that represents the display adapter.
old-location: display\dxgkddiadddevice.htm
old-project: display
ms.assetid: 5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiadddevice, DxgkDdiAddDevice callback function [Display Devices], DxgkDdiAddDevice, DXGKDDI_ADD_DEVICE, DXGKDDI_ADD_DEVICE, dispmprt/DxgkDdiAddDevice, DmFunctions_83323c62-42ac-45f5-80c8-b914fda642b5.xml
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
-	DxgkDdiAddDevice
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_ADD_DEVICE callback


## -description


The <i>DxgkDdiAddDevice</i> function creates a context block for a display adapter and returns a handle that represents the display adapter.


## -prototype


````
DXGKDDI_ADD_DEVICE DxgkDdiAddDevice;

NTSTATUS DxgkDdiAddDevice(
  _In_  const PDEVICE_OBJECT PhysicalDeviceObject,
  _Out_       PVOID          *MiniportDeviceContext
)
{ ... }
````


## -parameters




### -param PhysicalDeviceObject [in]

A pointer to a physical device object (PDO) that identifies a display adapter.


### -param MiniportDeviceContext [out]

A pointer to a variable that receives a handle, created by the display miniport driver, that will represent the display adapter identified by <i>PhysicalDeviceObject</i>. The display miniport driver can return <b>NULL</b> in this parameter to indicate that it will not support the display adapter identified by <i>PhysicalDeviceObject</i>. 


## -returns


<i>DxgkDdiAddDevice </i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.



## -remarks


The <i>DxgkDdiAddDevice</i> function allocates a private context block that is associated with the display adapter identified by <i>PhysicalDeviceObject</i>. You can think of the handle returned in <i>MiniportDeviceContext</i> as a handle to the display adapter or as a handle to the context block associated with the display adapter. The DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) will supply the handle in subsequent calls to the display miniport driver. The following list gives examples of various components of <i>Dxgkrnl.sys</i> passing the handle to functions implemented by the display miniport driver.
<ul>
<li>
The display port driver supplies the handle in the <i>MiniportDeviceContext</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function. 

</li>
<li>
The VidPN manager supplies the handle in the <i>hAdapter</i> parameter of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a> function. 

</li>
<li>
The DirectX graphics core supplies the handle in the <i>hAdapter</i> parameter of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.

</li>
</ul>Do not be confused by the fact that sometimes the handle is named <i>MiniportDeviceContext</i> and sometimes it is named <i>hAdapter</i>. Also, do not confuse this handle with the <i>hDevice</i> parameter that is passed to certain display miniport driver functions.

Some display adapter cards have two or more PCI functions that play the role of display adapter. For example, certain older cards implement multiple views by having a separate PCI function for each view. The display port driver calls<i> DxgkDdiAddDevice</i> once for each of those PCI functions, at which time the display miniport driver can indicate that it supports the PCI function (by setting <i>MiniportDeviceContext</i> to a nonzero value) or that it does not support the PCI function (by setting <i>MiniportDeviceContext</i> to <b>NULL</b>). To get information about a particular PCI function, the display miniport driver can pass <i>PhysicalDeviceObject</i> to <a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>.

In <a href="..\dispmprt\nc-dispmprt-dxgkddi_remove_device.md">DxgkDdiRemoveDevice</a>, free your context block and any other resources you allocate during <i>DxgkDdiAddDevice</i>.

The <i>DxgkDdiAddDevice</i> function should be made pageable.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_remove_device.md">DxgkDdiRemoveDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_ADD_DEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

