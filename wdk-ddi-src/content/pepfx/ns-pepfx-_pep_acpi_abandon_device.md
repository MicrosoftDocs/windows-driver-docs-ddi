---
UID: NS:pepfx._PEP_ACPI_ABANDON_DEVICE
title: _PEP_ACPI_ABANDON_DEVICE (pepfx.h)
description: The PEP_ACPI_ABANDON_DEVICE structure indicates whether the platform extension plug-in (PEP) accepts ownership of an abandoned device.
old-location: kernel\pep_acpi_abandon_device.htm
tech.root: kernel
ms.assetid: A8D0FA24-664F-4A2B-BF08-300D6E30F7E2
ms.date: 04/30/2018
keywords: ["_PEP_ACPI_ABANDON_DEVICE structure"]
ms.keywords: "*PPEP_ACPI_ABANDON_DEVICE, PEP_ACPI_ABANDON_DEVICE, PEP_ACPI_ABANDON_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_ABANDON_DEVICE, PPEP_ACPI_ABANDON_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_ABANDON_DEVICE, kernel.pep_acpi_abandon_device, pepfx/PEP_ACPI_ABANDON_DEVICE, pepfx/PPEP_ACPI_ABANDON_DEVICE"
f1_keywords:
 - "pepfx/PEP_ACPI_ABANDON_DEVICE"
 - "PEP_ACPI_ABANDON_DEVICE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_ACPI_ABANDON_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_ABANDON_DEVICE, *PPEP_ACPI_ABANDON_DEVICE
---

# _PEP_ACPI_ABANDON_DEVICE structure


## -description


The <b>PEP_ACPI_ABANDON_DEVICE</b> structure indicates whether the platform extension plug-in (PEP) accepts ownership of an abandoned device.


## -struct-fields




### -field AcpiDeviceName

[in] A pointer to an <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.


### -field DeviceAccepted

[out] Whether the PEP claims ownership of the device specified by the <b>AcpiDeviceName</b> member. Set to TRUE if the PEP claims ownership, and to FALSE if the PEP does not own the device.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_abandon_device">PEP_NOTIFY_ACPI_ABANDON_DEVICE</a> notification. This notification provides an opportunity for the PEP to clean up any remaining device state after the operating system has abandoned the device. The <b>AcpiDeviceName</b> member of the structure contains an input value that is supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The <b>DeviceAccepted</b> member contains an output value that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_abandon_device">PEP_NOTIFY_ACPI_ABANDON_DEVICE</a>
 

 

