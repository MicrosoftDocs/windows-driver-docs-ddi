---
UID: NS:dispmprt._DXGK_MIRACAST_INTERFACE
title: _DXGK_MIRACAST_INTERFACE
author: windows-driver-content
description: Contains pointers to functions in the Wireless display (Miracast) interface that the display miniport driver implements to create, destroy, query, and control Miracast device resources.
old-location: display\dxgk_miracast_display_interface.htm
old-project: display
ms.assetid: 39DCDA28-D32F-4755-91FB-0D42822D7B54
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dispmprt/DXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE, *PDXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE structure [Display Devices], dispmprt/PDXGK_MIRACAST_DISPLAY_INTERFACE, display.dxgk_miracast_display_interface, PDXGK_MIRACAST_DISPLAY_INTERFACE, PDXGK_MIRACAST_DISPLAY_INTERFACE structure pointer [Display Devices], _DXGK_MIRACAST_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Dispmprt.h
apiname: 
-	DXGK_MIRACAST_DISPLAY_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_DISPLAY_INTERFACE, *PDXGK_MIRACAST_DISPLAY_INTERFACE
---

# _DXGK_MIRACAST_INTERFACE structure


## -description


Contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn344651">Wireless display (Miracast) interface</a> that the display miniport driver implements to create, destroy, query, and control Miracast device resources.


## -syntax


````
typedef struct _DXGK_MIRACAST_INTERFACE {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              Context;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  DXGKDDI_MIRACAST_QUERY_CAPS        DxgkDdiMiracastQueryCaps;
  DXGKDDI_MIRACAST_CREATE_CONTEXT    DxgkDdiMiracastCreateContext;
  DXGKDDI_MIRACAST_HANDLE_IO_CONTROL DxgkDdiMiracastIoControl;
  DXGKDDI_MIRACAST_DESTROY_CONTEXT   DxgkDdiMiracastDestroyContext;
} DXGK_MIRACAST_DISPLAY_INTERFACE, *PDXGK_MIRACAST_DISPLAY_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the Miracast interface. Version number constants are defined in Dispmprt.h (for example, DXGK_MIRACAST_DISPLAY_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display miniport driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver.


### -field DxgkDdiMiracastQueryCaps

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_query_caps.md">DxgkDdiMiracastQueryCaps</a> function.


### -field DxgkDdiMiracastCreateContext

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function.


### -field DxgkDdiMiracastIoControl

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a> function.


### -field DxgkDdiMiracastDestroyContext

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_destroy_context.md">DxgkDdiMiracastDestroyContext</a> function.


## -remarks


When the graphics adapter is started, the Microsoft DirectX graphics kernel subsystem calls the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function to retrieve the interface.

If the driver does not support Miracast displays, it should fail the query for this interface.

If the driver supports Miracast displays, then it must also support High-bandwidth Digital Content Protection (HDCP).

For more info on how to use the Miracast interface, see <a href="https://msdn.microsoft.com/D67CAC4F-0409-4E8D-A31A-78C3EB473556">WDDM display miniport driver tasks to support Miracast wireless displays</a>.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_handle_io_control.md">DxgkDdiMiracastIoControl</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_query_caps.md">DxgkDdiMiracastQueryCaps</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_destroy_context.md">DxgkDdiMiracastDestroyContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MIRACAST_DISPLAY_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

