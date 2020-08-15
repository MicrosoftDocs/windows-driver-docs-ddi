---
UID: NF:storport.StorPortValidateRange
title: StorPortValidateRange function (storport.h)
description: The StorPortValidateRange routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems.
old-location: storage\storportvalidaterange.htm
tech.root: storage
ms.assetid: 505d6986-c59d-46b3-8437-29fc6a808ccd
ms.date: 03/29/2018
keywords: ["StorPortValidateRange function"]
ms.keywords: StorPortValidateRange, StorPortValidateRange routine [Storage Devices], storage.storportvalidaterange, storport/StorPortValidateRange, storprt_7d3583a5-211d-414e-880d-31c04145d3ab.xml
f1_keywords:
 - "storport/StorPortValidateRange"
 - "StorPortValidateRange"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortDeprecated
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
- StorPortValidateRange
targetos: Windows
req.typenames: 
---

# StorPortValidateRange function

## -description

The **StorPortValidateRange** routine determines whether a specified range of I/O addresses is in use by another adapter. This routine is obsolete in Windows NT 4.0 and later operating systems.

## -parameters

### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls [**StorPortInitialize**](nf-storport-storportinitialize.md). The port driver frees this memory when it removes the device.

### -param BusType 
[in]
Contains a value of type [**STORAGE_BUS_TYPE**](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff566356(v=vs.85)) that indicates the bus type.

### -param SystemIoBusNumber

Contains an integer identifying a system bus.

### -param IoAddress 
[in]
Contains the beginning address of the range of addresses to be validated.

### -param NumberOfBytes 
[in]
Contains the length in bytes of the range of addresses to be validated.

### -param InIoSpace 
[in]
Indicates, when **TRUE**, that the address range is in I/O space. If **FALSE**, the address is in memory space.

## -returns

**StorPortValidateRange** returns **TRUE** if a specified range of addresses is not claimed by another driver. This routine returns **FALSE** if another driver has claimed the address range.

## -remarks

For compatibility with older versions of Windows, this routine always returns **TRUE**.

Miniport drivers are given valid I/O ranges in the **AccessRanges** member of the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure when the Storport driver calls the miniport's [**HwStorFindAdapter**](nc-storport-hw_find_adapter.md) callback routine.

**StorPortValidateRange** uses **STOR_PHYSICAL_ADDRESS** to represent bus-relative addresses.

```cpp
typedef PHYSICAL_ADDRESS STOR_PHYSICAL_ADDRESS, *PSTOR_PHYSICAL_ADDRESS;
```

The **STOR_PHYSICAL_ADDRESS** type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address.

## -see-also

[**ScsiPortValidateRange**](../srb/nf-srb-scsiportvalidaterange.md)
