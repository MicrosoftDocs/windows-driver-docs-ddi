---
UID: NF:storport.StorPortInitialize
title: StorPortInitialize function (storport.h)
description: The StorPortInitialize routine initializes the port driver parameters and extension data. StorPortInitialize also saves the adapter information provided from the miniport driver.
old-location: storage\storportinitialize.htm
tech.root: storage
ms.assetid: b560ce42-3c5c-4766-bb9c-6590b7113ecd
ms.date: 03/29/2018
keywords: ["StorPortInitialize function"]
ms.keywords: StorPortInitialize, StorPortInitialize routine [Storage Devices], storage.storportinitialize, storport/StorPortInitialize, storprt_c60ad9af-507c-42e1-9f8a-04e3378bc37b.xml
f1_keywords:
 - "storport/StorPortInitialize"
 - "StorPortInitialize"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortInitialize
targetos: Windows
req.typenames: 
---

# StorPortInitialize function

## -description

The **StorPortInitialize** routine initializes the port driver parameters and extension data. **StorPortInitialize** also saves the adapter information provided from the [miniport driver](https://docs.microsoft.com/windows-hardware/drivers/storage/storage-miniport-drivers) **DriverEntry** routine.

## -parameters

### -param Argument1 [in]

The first pointer with which the operating system called the miniport's DriverEntry routine.

### -param Argument2 [in]

The second pointer with which the operating system called the miniports's DriverEntry routine.

### -param HwInitializationData [in]

Pointer to the initialization and configuration information set by the miniport driver in its DriverEntry routine.

### -param HwContext [in, optional]

Is the address of a context value to be passed to the miniport driver's [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) routine. Only legacy miniport drivers that scan the bus for HBAs rather than receiving configuration information from the port driver can use this parameter to store state between calls to **HwStorFindAdapter**.

## -returns

The result of the initialization actions performed by **StorPortInitialize**. The miniport driver will return this value as the return value for its DriverEntry routine.

**StorPortInitialize** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_INVALID_PARAMETER** | *Argument1* is NULL, or *Argument2* is NULL, OR *HwInitializationData* is NULL. |
| **STATUS_SUCCESS**           | The driver extension data and adapter information were initialized successfully. |
| **STATUS_NO_MEMORY**         | No memory is available to store an initialization parameter. |
| **STATUS_REVISION_MISMATCH** | The version of the structure pointed to by *HwInitializationData* is invalid for the current operating system. |
| **STATUS_INSUFFICENT_RESOURCES** | The allocation failed for the driver object extension data. |

## -remarks

This routine must be called from the miniport driver's **DriverEntry** routine.

Because Storport miniport drivers must support PnP, the Storport driver does not use the *HwContext* parameter passed to **StorPortInitialize**.

Every miniport driver's DriverEntry routine must call **StorPortInitialize** after the miniport driver has first zeroed and then set the members of [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md).

## -see-also

[**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md)

[**HwStorFindAdapter**](nc-storport-hw_find_adapter.md)
