---
UID: NS:pep_x._PEP_ACPI_REGISTER_DEVICE
title: _PEP_ACPI_REGISTER_DEVICE (pep_x.h)
description: The PEP_ACPI_REGISTER_DEVICE structure contains registration information about a device for which the platform extension plug-in (PEP) is to provide ACPI services.
old-location: kernel\pep_acpi_register_device.htm
tech.root: kernel
ms.assetid: 96FB6959-1583-42E0-9851-A09AE0CB73DB
ms.date: 04/30/2018
ms.keywords: "*PPEP_ACPI_REGISTER_DEVICE, PEP_ACPI_REGISTER_DEVICE, PEP_ACPI_REGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_REGISTER_DEVICE, PPEP_ACPI_REGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_REGISTER_DEVICE, kernel.pep_acpi_register_device, pepfx/PEP_ACPI_REGISTER_DEVICE, pepfx/PPEP_ACPI_REGISTER_DEVICE"
f1_keywords:
 - "pep_x/PEP_ACPI_REGISTER_DEVICE"
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
- PEP_ACPI_REGISTER_DEVICE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_REGISTER_DEVICE, *PPEP_ACPI_REGISTER_DEVICE
---

# _PEP_ACPI_REGISTER_DEVICE structure


## -description


The <b>PEP_ACPI_REGISTER_DEVICE</b> structure contains registration information about a device for which the platform extension plug-in (PEP) is to provide ACPI services.


## -struct-fields




### -field AcpiDeviceName

[in] An <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_string">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. The same name was previously supplied as an input value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_prepare_device">PEP_ACPI_PREPARE_DEVICE</a> notification for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.


### -field InputFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_REGISTER_DEVICE_INPUT_FLAG_NONE (0x0).


### -field KernelHandle

[in] A POHANDLE value that represents the registration of the device with the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The PEP can use this handle to identify the device in subsequent communications with PoFx.


### -field DeviceHandle

[out] A PEPHANDLE value that identifies the registration of this device for ACPI services. This handle is created by the PEP. In subsequent ACPI service notifications, PoFx will use this handle to identify the device.


### -field OutputFlags

[out] A set of output flags. No flags are currently defined for this member. Set this member to PEP_ACPI_REGISTER_DEVICE_OUTPUT_FLAG_NONE (0x0).


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification. The <b>AcpiDeviceName</b>, <b>InputFlags</b>, and <b>KernelHandle</b> members of the structure contain input values that are supplied by PoFx when this notification is sent to the PEP. The <b>DeviceHandle</b> and <b>OutputFlags</b> members contains output values that the PEP writes to this structure in response to the notification.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_prepare_device">PEP_ACPI_PREPARE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>
 

 

