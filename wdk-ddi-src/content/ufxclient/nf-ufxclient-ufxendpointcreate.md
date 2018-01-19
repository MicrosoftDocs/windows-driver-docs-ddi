---
UID: NF:ufxclient.UfxEndpointCreate
title: UfxEndpointCreate function
author: windows-driver-content
description: Creates an endpoint object.
old-location: buses\ufxendpointcreate.htm
old-project: usbref
ms.assetid: 060CADB7-AAC9-401A-9198-FC306CE74A34
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UfxEndpointCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxEndpointCreate
req.alt-loc: ufxclient.h
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
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxEndpointCreate function



## -description
Creates an endpoint object.



## -syntax

````
NTSTATUS UfxEndpointCreate(
  [in]           UFXDEVICE              UfxDevice,
  [in, out]      PUFXENDPOINT_INIT      EndpointInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [in]           PWDF_IO_QUEUE_CONFIG   TransferQueueConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES TransferQueueAttributes,
  [in]           PWDF_IO_QUEUE_CONFIG   CommandQueueConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES CommandQueueAttributes,
  [out]          UFXENDPOINT            *UfxEndpoint
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param EndpointInit [in, out]

Opaque structure passed by UFX in the call to <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_endpoint_add.md">EVT_UFX_DEVICE_ENDPOINT_ADD</a> or <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>.


### -param Attributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param TransferQueueConfig [in]

A pointer to a caller allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param TransferQueueAttributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param CommandQueueConfig [in]

A pointer to a caller allocated <a href="..\wdfio\ns-wdfio-_wdf_io_queue_config.md">WDF_IO_QUEUE_CONFIG</a> structure.  This structure must be initialized with <a href="..\wdfio\nf-wdfio-wdf_io_queue_config_init.md">WDF_IO_QUEUE_CONFIG_INIT</a>.


### -param CommandQueueAttributes [in, optional]

A pointer to caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This structure must be initialized with <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.


### -param UfxEndpoint [out]

A pointer to a location that receives a handle to a UFXENDPOINT object.


## -returns
If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.


## -remarks
  The transfer queue handles the following IOCTLs related to endpoint transfers:


The command queue will handle the following IOCTLs:

The following example shows how to create a UFXENDPOINT object and initialize its context.</p>