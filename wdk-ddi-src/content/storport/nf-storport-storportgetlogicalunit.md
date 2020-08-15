---
UID: NF:storport.StorPortGetLogicalUnit
title: StorPortGetLogicalUnit function (storport.h)
description: The StorPortGetLogicalUnit routine returns a pointer to the miniport driver's per-logical-unit storage area.
old-location: storage\storportgetlogicalunit.htm
tech.root: storage
ms.assetid: c8972d8b-9eba-4276-af63-1096a76b104f
ms.date: 03/29/2018
keywords: ["StorPortGetLogicalUnit function"]
ms.keywords: StorPortGetLogicalUnit, StorPortGetLogicalUnit routine [Storage Devices], storage.storportgetlogicalunit, storport/StorPortGetLogicalUnit, storprt_065c9617-06c6-4795-9743-14cd5803d9f9.xml
f1_keywords:
 - "storport/StorPortGetLogicalUnit"
 - "StorPortGetLogicalUnit"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
- StorPortGetLogicalUnit
targetos: Windows
req.typenames: 
---

# StorPortGetLogicalUnit function

## -description

The **StorPortGetLogicalUnit** routine returns a pointer to the miniport driver's per-logical-unit storage area.

## -parameters

### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver as soon as the miniport driver's [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) routine is called. The port driver frees this memory when it removes the device.

### -param PathId 
[in]
Identifies the SCSI bus.

### -param TargetId 
[in]
Identifies the target controller or device on the bus.

### -param Lun 
[in]
Identifies the logical unit (LU) number of the target device.

## -returns

**StorPortGetLogicalUnit** returns a pointer to the miniport driver's storage area for the requested logical unit. If the logical unit does not exist, it returns **NULL**.

## -remarks

**StorPortGetLogicalUnit** is irrelevant if the miniport driver's [**DriverEntry**](https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver") routine specified zero for the **LuExtensionSize** in the [**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md)
 when it called [**StorPortInitialize**](nf-storport-storportinitialize.md). Otherwise, the operating system-specific port driver allocates and initializes with zeros a set of LU extensions of the specified size for the miniport driver to use.

Per-LU storage can be used to store data relevant to a particular peripheral, such as saved data pointers. To access this area, the miniport driver calls **StorPortGetLogicalUnit** when the driver is maintaining information about the state of or current operation for any particular peripheral.

The operating system-specific port driver can consider a logical unit to be nonexistent if there is no active request for that logical unit and the device has never been successfully selected.

> [!NOTE]
>
> When the miniport driver calls **StorPortGetLogicalUnit** at IRQL = DISPATCH_LEVEL, the function acquires the interrupt lock. Calling **StorPortGetLogicalUnit** too often at this IRQL level impacts the performance and scalability of the miniport driver.

## -see-also

[**HW_INITIALIZATION_DATA**](ns-storport-_hw_initialization_data-r1.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)
