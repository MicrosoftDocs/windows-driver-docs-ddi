---
UID: NS:pepfx._PEP_WORK_ACPI_NOTIFY
title: _PEP_WORK_ACPI_NOTIFY (pepfx.h)
description: The PEP_WORK_ACPI_NOTIFY structure contains the ACPI Notify code for a device that has generated a hardware event.
old-location: kernel\pep_work_acpi_notify.htm
tech.root: kernel
ms.assetid: DFFDDF13-B8C7-4AB0-B2C9-9F34D19B21AE
ms.date: 04/30/2018
ms.keywords: "*PPEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY, PEP_WORK_ACPI_NOTIFY structure [Kernel-Mode Driver Architecture], PPEP_WORK_ACPI_NOTIFY, PPEP_WORK_ACPI_NOTIFY structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_ACPI_NOTIFY, kernel.pep_work_acpi_notify, pepfx/PEP_WORK_ACPI_NOTIFY, pepfx/PPEP_WORK_ACPI_NOTIFY"
ms.topic: struct
req.header: pepfx.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_WORK_ACPI_NOTIFY
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_ACPI_NOTIFY, *PPEP_WORK_ACPI_NOTIFY
---

# _PEP_WORK_ACPI_NOTIFY structure


## -description


The <b>PEP_WORK_ACPI_NOTIFY</b> structure contains the ACPI Notify code for a device that has generated a hardware event.


## -struct-fields




### -field DeviceHandle

A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) during the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification in which the PEP elected to provide ACPI services for the device.


### -field NotifyCode

The Notify code. For a list of Notify codes and their meanings, see section 5.6.6, "Device Object Notifications", of the [ACPI 5.0 specification](https://www.uefi.org/specifications).


## -remarks



The <b>AcpiNotify</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_ACPI_NOTIFY</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a>
 

 

