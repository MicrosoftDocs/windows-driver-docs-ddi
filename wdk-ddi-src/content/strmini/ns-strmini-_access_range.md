---
UID: NS:strmini._ACCESS_RANGE
title: _ACCESS_RANGE (strmini.h)
description: An ACCESS_RANGE describes a memory or I/O port range used by an HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\access_range.htm
tech.root: storage
ms.date: 08/26/2020
keywords: ["ACCESS_RANGE structure"]
ms.keywords: "*PACCESS_RANGE, ACCESS_RANGE, ACCESS_RANGE structure [Storage Devices], PACCESS_RANGE, PACCESS_RANGE structure pointer [Storage Devices], _ACCESS_RANGE, srb/ACCESS_RANGE, srb/PACCESS_RANGE, storage.access_range, structs-scsiport_353ffdeb-4d30-4df8-9422-ea3a9e662104.xml"
req.header: strmini.h
req.include-header: Srb.h, Storport.h, Strmini.h
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
req.irql: 
targetos: Windows
req.typenames: ACCESS_RANGE, *PACCESS_RANGE
req.product: Windows 10 or later.
f1_keywords:
 - _ACCESS_RANGE
 - strmini/_ACCESS_RANGE
 - PACCESS_RANGE
 - strmini/PACCESS_RANGE
 - ACCESS_RANGE
 - strmini/ACCESS_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - srb.h
api_name:
 - ACCESS_RANGE
---

# _ACCESS_RANGE structure (strmini.h)


## -description

An ACCESS_RANGE describes a memory or I/O port range used by an HBA.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver-overview) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field RangeStart

Contains an address of type [SCSI_PHYSICAL_ADDRESS](/previous-versions/ff565350(v=vs.85)) that specifies the bus-relative base address of the range. This is an address that can be passed into [ScsiPortGetDeviceBase](../srb/nf-srb-scsiportgetdevicebase.md).

### -field RangeLength

Specifies the size, in bytes, or number of ports in the range. A miniport driver must ensure that this value matches the range actually decoded by the adapter. For example, if the HBA uses seven registers but responds to eight, this member should be set to 8.

### -field RangeInMemory

Indicates the range is in memory when **TRUE**, rather than in I/O space. When **FALSE**, the range is in I/O space.

### -field Reserved

## -syntax

```cpp
typedef struct _ACCESS_RANGE {
  SCSI_PHYSICAL_ADDRESS RangeStart;
  ULONG                 RangeLength;
  BOOLEAN               RangeInMemory;
} ACCESS_RANGE, *PACCESS_RANGE;
```

## -remarks

Each ACCESS_RANGE is an **AccessRanges** array element within the PORT_CONFIGURATION_INFORMATION structure that is passed to a miniport driver's HwScsiFindAdapter routine.

If possible, the OS-specific port driver sets up each access range element with a bus-relative HBA range for the miniport driver before calling the miniport driver's HwScsiFindAdapter routine. Otherwise, the port driver zeros range elements for which it cannot supply configuration information.

If the port driver does supply a range, the miniport driver's HwScsiFindAdapter routine should use only the supplied addresses and should *never* attempt to find other HBAs on the same bus using addresses of its own devising. Attempting to access other bus-relative port or memory ranges when the port driver has supplied range information, particularly in x86-only systems in which some devices are initialized in x86 real mode, can cause other devices on the bus to fail initialization or even cause the system to fail the boot process.

Each miniport driver should have a set of bus-relative default ranges to try if the OS-specific port driver cannot supply the information. A miniport driver must call **ScsiPortValidateRange** to check the safety of any miniport driver-supplied access range *before* it attempts to map such a range with **ScsiPortGetDeviceBase** and use the returned logical addresses to access an adapter, particularly if one of its HBAs has a BIOS.

Any access range that a miniport driver fills in for the OS-specific port driver in the PORT_CONFIGURATION_INFORMATION must have the **RangeStart** member set to a bus-relative address, such as a value returned by **ScsiPortGetBusData**.

The corresponding base logical address returned by **ScsiPortGetDeviceBase** should be stored, usually in the miniport driver's device extension, as the **RangeStart** address for a mapped range of I/O ports or memory addresses used to call the **ScsiPortRead***Xxx* and **ScsiPortWrite***Xxx* routines.

## -see-also

[PORT_CONFIGURATION_INFORMATION (SCSI)](./ns-strmini-_port_configuration_information.md)

[ScsiPortGetBusData](../srb/nf-srb-scsiportgetbusdata.md)

[ScsiPortGetDeviceBase](../srb/nf-srb-scsiportgetdevicebase.md)

[ScsiPortValidateRange](../srb/nf-srb-scsiportvalidaterange.md)

[ScsiPortConvertUlongToPhysicalAddress](../srb/nf-srb-scsiportconvertulongtophysicaladdress.md)

[HwScsiFindAdapter](/previous-versions/windows/hardware/drivers/ff557300(v=vs.85))
