---
UID: NF:ntddk.IoGetConfigurationInformation
title: IoGetConfigurationInformation function
author: windows-driver-content
description: The IoGetConfigurationInformation routine returns a pointer to the I/O manager's global configuration information structure, which contains the current values for how many physical disk, floppy, CD-ROM, tape, SCSI HBA, serial, and parallel devices have device objects created to represent them by drivers as they are loaded.
old-location: kernel\iogetconfigurationinformation.htm
old-project: kernel
ms.assetid: 1d577588-72cf-44f2-b1bb-ebab0ee52fd6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetConfigurationInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetConfigurationInformation
req.alt-loc: NtosKrnl.exe
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetConfigurationInformation function



## -description
The <b>IoGetConfigurationInformation</b> routine returns a pointer to the I/O manager's global configuration information structure, which contains the current values for how many physical disk, floppy, CD-ROM, tape, SCSI HBA, serial, and parallel devices have device objects created to represent them by drivers as they are loaded.



## -syntax

````
PCONFIGURATION_INFORMATION IoGetConfigurationInformation(void);
````


## -parameters


## -returns
<b>IoGetConfigurationInformation</b> returns a pointer to the configuration information structure. This structure is defined as follows:

<b>IoGetConfigurationInformation</b> returns a pointer to the configuration information structure. This structure is defined as follows:

<b>IoGetConfigurationInformation</b> returns a pointer to the configuration information structure. This structure is defined as follows:


## -remarks
Certain types of device drivers can use the configuration information structure's values to construct device object names with appropriate digit suffixes when each driver creates its device objects. Note that the digit suffix for device object names is a zero-based count, while the counts maintained in the configuration information structure represent the number of device objects of a particular type already created. That is, the configuration information counts are one-based.

Any driver that calls <b>IoGetConfigurationInformation</b> must increment the count for its kind of device in this structure when it creates a device object to represent a physical device.

The system-supplied SCSI port driver supplies the count of SCSI HBAs present in the computer. SCSI class drivers can read this value to determine how many HBA-specific miniport drivers might control a SCSI bus with an attached device of the class driver's type.

The configuration information structure also contains a value indicating whether an already loaded driver has claimed either of the "AT" disk I/O address ranges.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546580">HalAssignSlotResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548285">IoAssignResources</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetConfigurationInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

