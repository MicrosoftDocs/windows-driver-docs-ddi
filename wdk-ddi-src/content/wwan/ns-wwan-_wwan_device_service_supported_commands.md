---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
title: "_WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.
old-location: netvista\wwan_device_service_supported_commands.htm
old-project: netvista
ms.assetid: 2AFE312D-8CCE-4A91-A23E-D5C6D2B0B01A
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, netvista.wwan_device_service_supported_commands, wwan/PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, wwan/WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure


## -description


The WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS structure represents a list of commands supported by a device service.


## -syntax


````
typedef struct _WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS {
  GUID             DeviceServiceGuid;
  WWAN_LIST_HEADER ListHeader;
} WWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS, *PWWAN_DEVICE_SERVICE_SUPPORTED_COMMANDS;
````


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service command.


### -field ListHeader

A formatted 
     <a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a> object that represents the
     list of commands supported by the device service.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_list_header.md">WWAN_LIST_HEADER</a>



 

 


