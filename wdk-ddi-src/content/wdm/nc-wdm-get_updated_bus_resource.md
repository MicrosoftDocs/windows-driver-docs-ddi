---
UID: NC:wdm.GET_UPDATED_BUS_RESOURCE
title: GET_UPDATED_BUS_RESOURCE
author: windows-driver-content
description: Reports the latest resource lists.
ms.assetid: d2624b1d-c2db-4240-ae78-1bda7efb8c7f
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	wdm.h
api_name: 
-	GET_UPDATED_BUS_RESOURCE
product: Windows
targetos: Windows
---

# GET_UPDATED_BUS_RESOURCE callback function

## -description

Reports the latest resource lists.

## -prototype

```
//Declaration

GET_UPDATED_BUS_RESOURCE GetUpdatedBusResource; 

// Definition

NTSTATUS GetUpdatedBusResource
(
	PVOID Context
	PCM_RESOURCE_LIST * UpdatedResourceList
	PCM_RESOURCE_LIST * UpdatedTranslatedResourceList
)
{...}

```

## -parameters

### -param Context
[In] A pointer to interface-specific context information. For this parameter, the caller supplies the value from the **Context** member of the [**BUS_RESOURCE_UPDATE_INTERFACE**](ns-wdm-_bus_resource_update_interface.md) structure for the interface.

### -param UpdatedResourceList
[Out] A pointer to the resource list in [**CM_RESOURCE_LIST**](ns-wdm-_cm_resource_list.md) structures that the driver used to detect the device. Resources in this list are in raw, untranslated form.

### -param UpdatedTranslatedResourceList
[Out] A pointer to the resource list in [**CM_RESOURCE_LIST**](ns-wdm-_cm_resource_list.md) structures. Resources in this list are translated.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The Pnp Manager invokes this callback function to query the bus driver for the latest resources.

Register the bus driver's implementation of this callback function by setting the **PGET_UPDATED_BUS_RESOURCE** member of [**BUS_RESOURCE_UPDATE_INTERFACE**](ns-wdm-_bus_resource_update_interface.md).


## -see-also