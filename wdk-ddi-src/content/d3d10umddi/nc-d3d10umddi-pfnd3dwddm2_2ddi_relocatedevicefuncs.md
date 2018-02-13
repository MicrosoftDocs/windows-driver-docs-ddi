---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The pfnRelocateDeviceFuncs callback function specifies the device functions table.
old-location: display\pfnd3dwddm2_2ddi_relocatedevicefuncs.htm
old-project: display
ms.assetid: EAABE65C-3893-4B4C-BB7E-A02F91F869BE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3dwddm2_2ddi_relocatedevicefuncs, pfnRelocateDeviceFuncs callback function [Display Devices], pfnRelocateDeviceFuncs, PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS, PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS, d3d10umddi/pfnRelocateDeviceFuncs
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnRelocateDeviceFuncs
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback


## -description


The <i>pfnRelocateDeviceFuncs</i> callback function specifies the device functions table. 


## -prototype


````
PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS pfnRelocateDeviceFuncs;

VOID APIENTRY* pfnRelocateDeviceFuncs(
       D3D10DDI_HDEVICE          hDevice,
  _In_ D3DWDDM2_2DDI_DEVICEFUNCS *DeviceFunctions
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice

The handle of a device.


#### - DeviceFunctions [in]

The device functions table, as a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

