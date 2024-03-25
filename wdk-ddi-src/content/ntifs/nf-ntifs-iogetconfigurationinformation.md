---
UID: NF:ntifs.IoGetConfigurationInformation
title: IoGetConfigurationInformation function (ntifs.h)
description: Learn more about the IoGetConfigurationInformation function.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoGetConfigurationInformation function"]
ms.keywords: IoGetConfigurationInformation, kernel.iogetconfigurationinformation, ntddk/IoGetConfigurationInformation
req.header: ntifs.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetConfigurationInformation
 - ntifs/IoGetConfigurationInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetConfigurationInformation
---

# IoGetConfigurationInformation function (ntifs.h)

## -description

The **IoGetConfigurationInformation** routine returns a pointer to the I/O manager's global configuration information structure, which contains the current values for how many physical disk, floppy, CD-ROM, tape, SCSI HBA, serial, and parallel devices have device objects created to represent them by drivers as they are loaded.

## -returns

**IoGetConfigurationInformation** returns a pointer to a [**CONFIGURATION_INFORMATION**](../ntddk/ns-ntddk-configuration_information.md) structure.

## -remarks

Certain types of device drivers can use the configuration information structure's values to construct device object names with appropriate digit suffixes when each driver creates its device objects. Note that the digit suffix for device object names is a zero-based count, while the counts maintained in the configuration information structure represent the number of device objects of a particular type already created. That is, the configuration information counts are one-based.

Any driver that calls **IoGetConfigurationInformation** must increment the count for its kind of device in this structure when it creates a device object to represent a physical device.

The system-supplied SCSI port driver supplies the count of SCSI HBAs present in the computer. SCSI class drivers can read this value to determine how many HBA-specific miniport drivers might control a SCSI bus with an attached device of the class driver's type.

The configuration information structure also contains a value indicating whether an already loaded driver has claimed either of the "AT" disk I/O address ranges.

## -see-also

[HalAssignSlotResources](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalGetBusData](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[HalGetBusDataByOffset](/previous-versions/windows/hardware/drivers/ff546644(v=vs.85))

[IoAssignResources](/windows-hardware/drivers/kernel/mmcreatemdl)

[IoQueryDeviceDescription](/windows-hardware/drivers/kernel/mmcreatemdl)

[IoReportResourceUsage](/windows-hardware/drivers/kernel/mmcreatemdl)
