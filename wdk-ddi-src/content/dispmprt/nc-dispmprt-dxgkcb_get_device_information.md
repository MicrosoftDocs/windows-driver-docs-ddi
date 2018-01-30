---
UID: NC:dispmprt.DXGKCB_GET_DEVICE_INFORMATION
title: DXGKCB_GET_DEVICE_INFORMATION
author: windows-driver-content
description: The DxgkCbGetDeviceInformation function gets information, including the registry path and a list of translated resources, about a specified display adapter.
old-location: display\dxgkcbgetdeviceinformation.htm
old-project: display
ms.assetid: cb627eab-93b9-49c5-bd35-4a57220366e7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbgetdeviceinformation, DxgkCbGetDeviceInformation callback function [Display Devices], DxgkCbGetDeviceInformation, DXGKCB_GET_DEVICE_INFORMATION, DXGKCB_GET_DEVICE_INFORMATION, dispmprt/DxgkCbGetDeviceInformation, DpFunctions_e2d65bd6-c28f-46db-acf1-b88ececedb08.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	Dispmprt.h
apiname:
-	DxgkCbGetDeviceInformation
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKCB_GET_DEVICE_INFORMATION callback


## -description


The <i>DxgkCbGetDeviceInformation</i> function gets information, including the registry path and a list of translated resources, about a specified display adapter.


## -prototype


````
DXGKCB_GET_DEVICE_INFORMATION DxgkCbGetDeviceInformation;

NTSTATUS DxgkCbGetDeviceInformation(
  _In_  HANDLE            DeviceHandle,
  _Out_ PDXGK_DEVICE_INFO DeviceInfo
)
{ ... }
````


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param DeviceInfo [out]

A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_device_info.md">DXGK_DEVICE_INFO</a> structure that receives information about the display adapter.


## -returns


<i>DxgkCbGetDeviceInformation</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_INVALID_PARAMETER.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

<a href="..\dispmprt\ns-dispmprt-_dxgk_device_info.md">DXGK_DEVICE_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_GET_DEVICE_INFORMATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

