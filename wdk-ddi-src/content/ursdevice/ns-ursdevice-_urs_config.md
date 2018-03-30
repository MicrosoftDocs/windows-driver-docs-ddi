---
UID: NS:ursdevice._URS_CONFIG
title: "_URS_CONFIG"
author: windows-driver-content
description: Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling URS_CONFIG_INIT.
old-location: buses\urs_config.htm
old-project: usbref
ms.assetid: 3857CA53-6992-410A-96D1-EEA9CC586EDF
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PURS_CONFIG, PURS_CONFIG, PURS_CONFIG structure pointer [Buses], URS_CONFIG, URS_CONFIG structure [Buses], _URS_CONFIG, buses.urs_config, ursdevice/PURS_CONFIG, ursdevice/URS_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
-	Ursdevice.h
api_name:
-	URS_CONFIG
product: Windows
targetos: Windows
req.typenames: URS_CONFIG, *PURS_CONFIG
req.product: Windows 10 or later.
---

# _URS_CONFIG structure


## -description


Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628021">URS_CONFIG_INIT</a>.


## -struct-fields




### -field Size

The size of this structure.


### -field HostInterfaceType

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628023">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of USB host controller: EHCI, xHCI, or other.


### -field EvtUrsFilterRemoveResourceRequirements

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function.


### -field EvtUrsSetRole

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595922">EVT_URS_SET_ROLE</a> callback function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt628021">URS_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a>
 

 

