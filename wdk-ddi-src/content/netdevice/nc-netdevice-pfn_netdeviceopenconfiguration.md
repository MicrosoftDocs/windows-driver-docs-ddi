---
UID: NC:netdevice.PFN_NETDEVICEOPENCONFIGURATION
title: PFN_NETDEVICEOPENCONFIGURATION
author: windows-driver-content
description: 
ms.assetid: fac43744-51e8-4ba5-be5e-34b46abcc2c8
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netdevice.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	netdevice.h
api_name: 
-	PFN_NETDEVICEOPENCONFIGURATION
product: Windows
targetos: Windows
---

# PFN_NETDEVICEOPENCONFIGURATION callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFN_NETDEVICEOPENCONFIGURATION PfnNetdeviceopenconfiguration; 

// Definition

WDFAPI PfnNetdeviceopenconfiguration 
(
	PNET_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE Device
	PWDF_OBJECT_ATTRIBUTES ConfigurationAttributes
	NETCONFIGURATION *Configuration
)
{...}

```

## -parameters

### -param DriverGlobals: 
### -param Device: 
### -param ConfigurationAttributes: 
### -param *Configuration: 



## -returns

Returns WDFAPI that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also