---
UID: NS:wwan._WWAN_DEVICE_SERVICE_COMMAND
title: _WWAN_DEVICE_SERVICE_COMMAND (wwan.h)
description: The WWAN_DEVICE_SERVICE_COMMAND structure represents a device service command.
old-location: netvista\wwan_device_service_command.htm
tech.root: netvista
ms.assetid: 475D7ECF-B8A8-445D-8ED7-029BD57C8C48
ms.date: 05/02/2018
keywords: ["_WWAN_DEVICE_SERVICE_COMMAND structure"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_COMMAND, PWWAN_DEVICE_SERVICE_COMMAND, PWWAN_DEVICE_SERVICE_COMMAND structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_COMMAND, WWAN_DEVICE_SERVICE_COMMAND structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_COMMAND, netvista.wwan_device_service_command, wwan/PWWAN_DEVICE_SERVICE_COMMAND, wwan/WWAN_DEVICE_SERVICE_COMMAND"
f1_keywords:
 - "wwan/WWAN_DEVICE_SERVICE_COMMAND"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_DEVICE_SERVICE_COMMAND
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_COMMAND, *PWWAN_DEVICE_SERVICE_COMMAND
---

# _WWAN_DEVICE_SERVICE_COMMAND structure


## -description


The WWAN_DEVICE_SERVICE_COMMAND structure represents a device service command.


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service that the command targets.


### -field CommandID

The ID for the command.


### -field uDataSize

The size, in bytes, of the device service command data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## -remarks



Device service command OIDs use this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
 

 

