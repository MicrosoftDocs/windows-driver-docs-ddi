---
UID: NF:ucmucsidevice.UCMUCSI_DEVICE_CONFIG_INIT
title: UCMUCSI_DEVICE_CONFIG_INIT function
author: windows-driver-content
tech.root: usbref
description: Initializes a **UCMUCSI_DEVICE_CONFIG** structure.
ms.assetid: a70f1d65-e06e-48ed-be3d-f099fa01d475
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UCMUCSI_DEVICE_CONFIG_INIT
req.header: ucmucsidevice.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
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
-	LibDef
api_location: 
-	UcmUcsiCxStub.lib
api_name: 
-	UcmUcsiDeviceInitialize
product: Windows
targetos: Windows



---

# UCMUCSI_DEVICE_CONFIG_INIT function


## -description

Initializes a [**UCMUCSI_DEVICE_CONFIG**](ns-ucmucsidevice-_ucmucsi_device_config.md) structure.

## -parameters

### -param Config
A pointer to the **UCMUCSI_DEVICE_CONFIG** structure to initialize.

## -returns
This function returns VOID.

## -remarks
The client driver must call this initialization function before calling [**UcmUcsiDeviceInitialize**](nf-ucmucsidevice-ucmucsideviceinitialize.md).

## -see-also

[**EVT_WDF_DRIVER_DEVICE_ADD**](https://msdn.microsoft.com/library/windows/hardware/ff541693)

[**UCMUCSI_DEVICE_CONFIG**](ns-ucmucsidevice-_ucmucsi_device_config.md)

[**WdfDeviceCreate**](https://msdn.microsoft.com/library/windows/hardware/ff545926)
