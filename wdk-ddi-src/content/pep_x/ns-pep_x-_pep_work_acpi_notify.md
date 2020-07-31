---
UID: NS:pep_x._PEP_WORK_ACPI_NOTIFY
title: _PEP_WORK_ACPI_NOTIFY (pep_x.h)
description: The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event.
old-location: kernel\pep_work_acpi_notify.htm
tech.root: kernel
ms.assetid: DFFDDF13-B8C7-4AB0-B2C9-9F34D19B21AE
ms.date: 04/30/2018
keywords: ["_PEP_WORK_ACPI_NOTIFY structure"]
ms.keywords: "*PPEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY structure [Kernel-Mode Driver Architecture], PPEP_WORK_ACPI_NOTIFY, PPEP_WORK_ACPI_NOTIFY structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_ACPI_NOTIFY, kernel.pep_work_acpi_notify, pepfx/PEP_WORK_ACPI_NOTIFY, pepfx/PPEP_WORK_ACPI_NOTIFY"
f1_keywords:
 - "pep_x/PEP_WORK_ACPI_NOTIFY"
 - "PEP_WORK_ACPI_NOTIFY"
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- pepfx.h
api_name:
- PEP_WORK_ACPI_NOTIFY
targetos: Windows
req.typenames: PEP_WORK_ACPI_NOTIFY, *PPEP_WORK_ACPI_NOTIFY
---

# _PEP_WORK_ACPI_NOTIFY structure


## -description


The <b>PEP_WORK_ACPI_NOTIFY</b> structure contains the ACPI Notify code for a device that has generated a hardware event.


## -struct-fields




### -field DeviceHandle

A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification in which the PEP elected to provide ACPI services for the device.


### -field NotifyCode

The Notify code. For a list of Notify codes and their meanings, see section 5.6.6, "Device Object Notifications", of the [ACPI 5.0 specification](https://uefi.org/specifications).


## -remarks



The <b>AcpiNotify</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_ACPI_NOTIFY</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>
 

 

