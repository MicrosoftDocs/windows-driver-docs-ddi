---
UID: NS:srb._ACCESS_RANGE
title: "_ACCESS_RANGE"
author: windows-driver-content
description: An ACCESS_RANGE describes a memory or I/O port range used by an HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\access_range.htm
old-project: storage
ms.assetid: 6009d11b-4f44-4591-bcb8-66e0c42d5689
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PACCESS_RANGE, _ACCESS_RANGE, PACCESS_RANGE structure pointer [Storage Devices], PACCESS_RANGE, ACCESS_RANGE, srb/ACCESS_RANGE, structs-scsiport_353ffdeb-4d30-4df8-9422-ea3a9e662104.xml, storage.access_range, srb/PACCESS_RANGE, ACCESS_RANGE structure [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: srb.h
req.include-header: Srb.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	srb.h
apiname:
-	ACCESS_RANGE
product: Windows
targetos: Windows
req.typenames: "*PACCESS_RANGE, ACCESS_RANGE"
req.product: Windows 10 or later.
---

# _ACCESS_RANGE structure


## -description


An ACCESS_RANGE describes a memory or I/O port range used by an HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _ACCESS_RANGE {
  SCSI_PHYSICAL_ADDRESS RangeStart;
  ULONG                 RangeLength;
  BOOLEAN               RangeInMemory;
} ACCESS_RANGE, *PACCESS_RANGE;
````


## -struct-fields




### -field RangeStart

Contains an address of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff565350">SCSI_PHYSICAL_ADDRESS</a> that specifies the bus-relative base address of the range. This is an address that can be passed into <a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>.


### -field RangeLength

Specifies the size, in bytes, or number of ports in the range. A miniport driver must ensure that this value matches the range actually decoded by the adapter. For example, if the HBA uses seven registers but responds to eight, this member should be set to 8.


### -field RangeInMemory

Indicates the range is in memory when <b>TRUE</b>, rather than in I/O space. When <b>FALSE</b>, the range is in I/O space. 


## -remarks


Each ACCESS_RANGE is an <b>AccessRanges</b> array element within the PORT_CONFIGURATION_INFORMATION structure that is passed to a miniport driver's HwScsiFindAdapter routine.

If possible, the OS-specific port driver sets up each access range element with a bus-relative HBA range for the miniport driver before calling the miniport driver's HwScsiFindAdapter routine. Otherwise, the port driver zeros range elements for which it cannot supply configuration information.

If the port driver does supply a range, the miniport driver's HwScsiFindAdapter routine should use only the supplied addresses and should <i>never</i> attempt to find other HBAs on the same bus using addresses of its own devising. Attempting to access other bus-relative port or memory ranges when the port driver has supplied range information, particularly in x86-only systems in which some devices are initialized in x86 real mode, can cause other devices on the bus to fail initialization or even cause the system to fail the boot process.

Each miniport driver should have a set of bus-relative default ranges to try if the OS-specific port driver cannot supply the information. A miniport driver must call <b>ScsiPortValidateRange</b> to check the safety of any miniport driver-supplied access range <i>before</i> it attempts to map such a range with <b>ScsiPortGetDeviceBase</b> and use the returned logical addresses to access an adapter, particularly if one of its HBAs has a BIOS.

Any access range that a miniport driver fills in for the OS-specific port driver in the PORT_CONFIGURATION_INFORMATION must have the <b>RangeStart</b> member set to a bus-relative address, such as a value returned by <b>ScsiPortGetBusData</b>.

The corresponding base logical address returned by <b>ScsiPortGetDeviceBase</b> should be stored, usually in the miniport driver's device extension, as the <b>RangeStart</b> address for a mapped range of I/O ports or memory addresses used to call the <b>ScsiPortRead</b><i>Xxx</i> and <b>ScsiPortWrite</b><i>Xxx</i> routines.



## -see-also

<a href="..\srb\nf-srb-scsiportgetbusdata.md">ScsiPortGetBusData</a>

<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

<a href="..\srb\nf-srb-scsiportvalidaterange.md">ScsiPortValidateRange</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>

<a href="..\srb\nf-srb-scsiportconvertulongtophysicaladdress.md">ScsiPortConvertUlongToPhysicalAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ACCESS_RANGE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

