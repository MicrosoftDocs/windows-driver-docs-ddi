---
UID: NS:usbfnbase._USBFN_BUS_CONFIGURATION_INFO
title: _USBFN_BUS_CONFIGURATION_INFO
author: windows-driver-content
description: Configuration packet that stores information about an available USB configuration.
old-location: buses\usbfn_bus_configuration_info.htm
old-project: usbref
ms.assetid: 26F11BC8-0F43-4E52-B2E1-2C3C6B327CF0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBFN_BUS_CONFIGURATION_INFO, _USBFN_BUS_CONFIGURATION_INFO, usbfnbase/USBFN_BUS_CONFIGURATION_INFO, *PUSBFN_BUS_CONFIGURATION_INFO, PUSBFN_BUS_CONFIGURATION_INFO structure pointer [Buses], USBFN_BUS_CONFIGURATION_INFO structure [Buses], usbfnbase/PUSBFN_BUS_CONFIGURATION_INFO, buses.usbfn_bus_configuration_info, PUSBFN_BUS_CONFIGURATION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	usbfnbase.h
apiname: 
-	USBFN_BUS_CONFIGURATION_INFO
product: Windows
targetos: Windows
req.typenames: *PUSBFN_BUS_CONFIGURATION_INFO, USBFN_BUS_CONFIGURATION_INFO
req.product: Windows 10 or later.
---

# _USBFN_BUS_CONFIGURATION_INFO structure


## -description


Configuration packet that stores information about 
an available USB configuration.


## -syntax


````
typedef struct _USBFN_BUS_CONFIGURATION_INFO {
  WCHAR    ConfigurationName[MAX_CONFIGURATION_NAME_LENGTH];
  BOOLEAN  IsCurrent;
  BOOLEAN  IsActive;
} USBFN_BUS_CONFIGURATION_INFO, *PUSBFN_BUS_CONFIGURATION_INFO;
````


## -struct-fields




### -field ConfigurationName

A NULL-terminated string that indicates the name of a configuration.


### -field IsCurrent

Indicates whether this configuration is the 
    current configuration.


### -field IsActive

    Indicates whether the configuration is active. This is a read-only information that is returned by USB function class extension (UFX) and is ignored in requests sent to UFX.


