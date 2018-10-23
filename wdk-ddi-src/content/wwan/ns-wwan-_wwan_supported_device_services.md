---
UID: NS:wwan._WWAN_SUPPORTED_DEVICE_SERVICES
title: "_WWAN_SUPPORTED_DEVICE_SERVICES"
author: windows-driver-content
description: The WWAN_SUPPORTED_DEVICE_SERVICES structure describes information about device services supported by the miniport driver.
old-location: netvista\wwan_supported_device_services.htm
tech.root: netvista
ms.assetid: CFCF122F-E971-4A6B-91C9-71A8030366A9
ms.date: 05/02/2018
ms.keywords: "*PWWAN_SUPPORTED_DEVICE_SERVICES, PWWAN_SUPPORTED_DEVICE_SERVICES, PWWAN_SUPPORTED_DEVICE_SERVICES structure pointer [Network Drivers Starting with Windows Vista], WWAN_SUPPORTED_DEVICE_SERVICES, WWAN_SUPPORTED_DEVICE_SERVICES structure [Network Drivers Starting with Windows Vista], _WWAN_SUPPORTED_DEVICE_SERVICES, netvista.wwan_supported_device_services, wwan/PWWAN_SUPPORTED_DEVICE_SERVICES, wwan/WWAN_SUPPORTED_DEVICE_SERVICES"
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
-	WWAN_SUPPORTED_DEVICE_SERVICES
product:
- Windows
targetos: Windows
req.typenames: WWAN_SUPPORTED_DEVICE_SERVICES, *PWWAN_SUPPORTED_DEVICE_SERVICES
---

# _WWAN_SUPPORTED_DEVICE_SERVICES structure


## -description


The WWAN_SUPPORTED_DEVICE_SERVICES structure describes information about device services supported by the miniport driver.


## -struct-fields




### -field uMaxCommandDataSize

The maximum size, in bytes, of data that can be associated with a device service command.


### -field uMaxSessionDataSize

The maximum size, in bytes, of data that can be associated with a device service session.


### -field uMaxSessionCount

The maximum number of device service sessions supported by the miniport driver.


### -field ListHeader

A formatted WWAN_LIST_HEADER object that represents a list of supported device services and the number of services  in the list.

This member points to the list of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831870">WWAN_DEVICE_SERVICE_ENTRY</a> by using the WWAN_LIST_HEADER structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831867">NDIS_WWAN_SUPPORTED_DEVICE_SERVICES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831870">WWAN_DEVICE_SERVICE_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571208">WWAN_LIST_HEADER</a>
 

 

