---
UID: NS:ucxusbdevice._UCX_USBDEVICE_EVENT_CALLBACKS
title: "_UCX_USBDEVICE_EVENT_CALLBACKS" (ucxusbdevice.h)
description: This structure provides a list of UCX USB device event callback functions.
old-location: buses\_ucx_usbdevice_event_callbacks.htm
tech.root: usbref
ms.assetid: 7A320D48-E71C-40FE-A2EF-201CFCE55145
ms.date: 05/07/2018
ms.keywords: "*PUCX_USBDEVICE_EVENT_CALLBACKS, P_UCX_USBDEVICE_EVENT_CALLBACKS, P_UCX_USBDEVICE_EVENT_CALLBACKS structure pointer [Buses], UCX_USBDEVICE_EVENT_CALLBACKS, UCX_USBDEVICE_EVENT_CALLBACKS structure [Buses], _UCX_USBDEVICE_EVENT_CALLBACKS, buses._ucx_usbdevice_event_callbacks, ucxusbdevice/P_UCX_USBDEVICE_EVENT_CALLBACKS, ucxusbdevice/_UCX_USBDEVICE_EVENT_CALLBACKS"
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	UCX_USBDEVICE_EVENT_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_EVENT_CALLBACKS, *PUCX_USBDEVICE_EVENT_CALLBACKS
---

# _UCX_USBDEVICE_EVENT_CALLBACKS structure


## -description


This structure provides a list of UCX USB device event callback functions.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field EvtUsbDeviceEndpointsConfigure

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187842">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a> callback function.


### -field EvtUsbDeviceEnable

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187841">EVT_UCX_USBDEVICE_ENABLE</a> callback function.


### -field EvtUsbDeviceDisable

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187840">EVT_UCX_USBDEVICE_DISABLE</a> callback function.


### -field EvtUsbDeviceReset

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187845">EVT_UCX_USBDEVICE_RESET</a> callback function.


### -field EvtUsbDeviceAddress

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187838">EVT_UCX_USBDEVICE_ADDRESS</a> callback function.


### -field EvtUsbDeviceUpdate

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187846">EVT_UCX_USBDEVICE_UPDATE</a> callback function.


### -field EvtUsbDeviceHubInfo

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187844">EVT_UCX_USBDEVICE_HUB_INFO</a> callback function.


### -field EvtUsbDeviceDefaultEndpointAdd

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187839">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a> callback function.


### -field EvtUsbDeviceEndpointAdd

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt187843">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> callback function.


### -field EvtUsbDeviceSuspend

A pointer to an <a href="https://msdn.microsoft.com/809F946C-DDD4-4C4D-9F0F-F2B4A4657D12">EVT_UCX_USBDEVICE_SUSPEND</a> callback function.


### -field EvtUsbDeviceResume

A pointer to an <a href="https://msdn.microsoft.com/876D9754-B3AA-42C5-8BDD-60CFD4F78951">EVT_UCX_USBDEVICE_RESUME</a> callback function.


### -field EvtUsbDeviceGetCharacteristic

A pointer to an <a href="https://msdn.microsoft.com/EE8568F6-3D88-477E-9F0D-044D014EBCF3">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a> callback function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188068">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt188053">UcxUsbDeviceInitSetEventCallbacks</a>
 

 

