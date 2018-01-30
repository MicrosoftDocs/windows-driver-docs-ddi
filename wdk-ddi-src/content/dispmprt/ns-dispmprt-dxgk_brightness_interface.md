---
UID: NS:dispmprt.DXGK_BRIGHTNESS_INTERFACE
title: DXGK_BRIGHTNESS_INTERFACE
author: windows-driver-content
description: The DXGK_BRIGHTNESS_INTERFACE structure contains pointers to functions in the Panel Brightness Control Interface, which is implemented by the display miniport driver.
old-location: display\dxgk_brightness_interface.htm
old-project: display
ms.assetid: 8fa7908c-7ed4-4f85-846c-71fc5c7dc035
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgk_brightness_interface, DXGK_BRIGHTNESS_INTERFACE, PDXGK_BRIGHTNESS_INTERFACE structure pointer [Display Devices], PDXGK_BRIGHTNESS_INTERFACE, DXGK_BRIGHTNESS_INTERFACE structure [Display Devices], dispmprt/PDXGK_BRIGHTNESS_INTERFACE, DmStructs_f750f3c3-0754-49b9-8ad5-cd93f84697c4.xml, *PDXGK_BRIGHTNESS_INTERFACE, dispmprt/DXGK_BRIGHTNESS_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_BRIGHTNESS_INTERFACE
product: Windows
targetos: Windows
req.typenames: "*PDXGK_BRIGHTNESS_INTERFACE, DXGK_BRIGHTNESS_INTERFACE"
---

# DXGK_BRIGHTNESS_INTERFACE structure


## -description


The <b>DXGK_BRIGHTNESS_INTERFACE</b> structure contains pointers to functions in the Panel Brightness Control Interface, which is implemented by the display miniport driver.


## -syntax


````
typedef struct {
  USHORT                       Size;
  USHORT                       Version;
  PVOID                        Context;
  PINTERFACE_REFERENCE         InterfaceReference;
  PINTERFACE_DEREFERENCE       InterfaceDereference;
  DXGK_BRIGHTNESS_GET_POSSIBLE GetPossibleBrightness;
  DXGK_BRIGHTNESS_SET          SetBrightness;
  DXGK_BRIGHTNESS_GET          GetBrightness;
} DXGK_BRIGHTNESS_INTERFACE, *PDXGK_BRIGHTNESS_INTERFACE;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the brightness interface. Version number constants are defined in Dispmprt.h (for example, <b>DXGK_BRIGHTNESS_INTERFACE_VERSION_1</b>).


### -field Context

A pointer to a private context block.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver.


### -field GetPossibleBrightness

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_possible.md">DxgkDdiGetPossibleBrightness</a> function.


### -field SetBrightness

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a> function.


### -field GetBrightness

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get.md">DxgkDdiGetBrightness</a> function.


## -remarks


A kernel-mode component that must use the brightness interface initiates a call to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function to retrieve the interface and passes GUID_DEVINTERFACE_BRIGHTNESS in the <b>InterfaceType</b> member of the <a href="..\video\ns-video-_query_interface.md">QUERY_INTERFACE</a> structure that the <i>QueryInterface</i> parameter points to.



## -see-also

<a href="..\dispmprt\ns-dispmprt-dxgk_brightness_interface_2.md">DXGK_BRIGHTNESS_INTERFACE_2</a>

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get_possible.md">DxgkDdiGetPossibleBrightness</a>

<a href="..\video\ns-video-_query_interface.md">QUERY_INTERFACE</a>

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_get.md">DxgkDdiGetBrightness</a>

<a href="..\dispmprt\nc-dispmprt-dxgk_brightness_set.md">DxgkDdiSetBrightness</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_BRIGHTNESS_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

