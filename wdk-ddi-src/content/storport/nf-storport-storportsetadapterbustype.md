---
UID: NF:storport.StorPortSetAdapterBusType
title: StorPortSetAdapterBusType function (storport.h)
description: StorPortSetAdapterBusType is used to adjust the bus type of the adapter depending on its current configuration.
old-location: storage\storportsetadapterbustype.htm
tech.root: storage
ms.date: 04/21/2021
keywords: ["StorPortSetAdapterBusType function"]
ms.keywords: StorPortSetAdapterBusType, StorPortSetAdapterBusType routine [Storage Devices], storage.storportsetadapterbustype, storport/StorPortSetAdapterBusType
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortSetAdapterBusType
 - storport/StorPortSetAdapterBusType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortSetAdapterBusType
---

# StorPortSetAdapterBusType function

## -description

**StorPortSetAdapterBusType** is used to adjust the bus type of the adapter depending on its current configuration.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls [**StorPortInitialize**](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device.

### -param BusType

[in] Contains a [**STORAGE_BUS_TYPE**](../ntddstor/ne-ntddstor-storage_bus_type.md) value that specifies the type of bus-specific configuration data to be set.

## -returns

The **StorPortSetAdapterBusType** routine returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_UNSUCCESSFUL | This routine was called outside the [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) function. |
| STOR_STATUS_SUCCESS      | This routine completed successfully. |
| STOR_STATUS_INVALID_PARAMETER | BusType is an invalid value. |

## -remarks

 Setting the **BusType** with this routine will allow you to override the global property set in the miniport INF without having to re-install the driver. This is useful for scenarios such as RAID support or support for multiple adapters with a different bus type.
