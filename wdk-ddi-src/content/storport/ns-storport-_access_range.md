---
UID: NS:storport._ACCESS_RANGE
title: _ACCESS_RANGE (storport.h)
description: An ACCESS_RANGE describes a memory or I/O port range used by an HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\access_range.htm
tech.root: storage
ms.assetid: 6009d11b-4f44-4591-bcb8-66e0c42d5689
ms.date: 04/03/2020
keywords: ["_ACCESS_RANGE structure"]
ms.keywords: "*PACCESS_RANGE, ACCESS_RANGE, ACCESS_RANGE structure [Storage Devices], PACCESS_RANGE, PACCESS_RANGE structure pointer [Storage Devices], _ACCESS_RANGE, srb/ACCESS_RANGE, srb/PACCESS_RANGE, storage.access_range, structs-scsiport_353ffdeb-4d30-4df8-9422-ea3a9e662104.xml"
f1_keywords:
 - "storport/ACCESS_RANGE"
 - "ACCESS_RANGE"
req.header: storport.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- srb.h
api_name:
- ACCESS_RANGE
targetos: Windows
req.typenames: ACCESS_RANGE, *PACCESS_RANGE
---

# _ACCESS_RANGE structure

## -description

An ACCESS_RANGE describes a memory or I/O port range used by an HBA.

## -struct-fields

### -field RangeStart

Contains a physical address that specifies the bus-relative base address of a range used by the HBA. The value of this member can be obtained from one of the **AccessRanges** elements in the [**PORT_CONFIGURATION_INFORMATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_port_configuration_information) structure. This is an address that can be passed into [**StorPortGetDeviceBase**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase).

### -field RangeLength

Specifies the size, in bytes, or number of ports in the range. A miniport driver must ensure that this value matches the range actually decoded by the adapter. For example, if the HBA uses seven registers but responds to eight, this member should be set to 8.

### -field RangeInMemory

Indicates the range is in memory when **TRUE**, rather than in I/O space. When **FALSE**, the range is in I/O space.

## -remarks

Each ACCESS_RANGE is an **AccessRanges** array element within the [**PORT_CONFIGURATION_INFORMATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_port_configuration_information) structure that is passed to a miniport driver's [**HwStorFindAdapter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter) routine.

Storport allocates memory for the access ranges and initializes the **AccessRanges** member. The miniport driver's **HwStorFindAdapter** routine should use only the supplied addresses and should *never* attempt to find other HBAs on the same bus using addresses of its own devising. Attempting to access other bus-relative port or memory ranges when the port driver has supplied range information, particularly in x86-only systems in which some devices are initialized in x86 real mode, can cause other devices on the bus to fail initialization or even cause the system to fail the boot process.

## -see-also

[**HwStorFindAdapter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter)

[**PORT_CONFIGURATION_INFORMATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_port_configuration_information)

[**StorPortGetDeviceBase**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase)
