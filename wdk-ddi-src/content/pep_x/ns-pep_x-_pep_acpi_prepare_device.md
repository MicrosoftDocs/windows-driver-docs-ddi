---
UID: NS:pep_x._PEP_ACPI_PREPARE_DEVICE
title: _PEP_ACPI_PREPARE_DEVICE (pep_x.h)
description: The PEP_ACPI_PREPARE_DEVICE structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.
old-location: kernel\pep_acpi_prepare_device.htm
tech.root: kernel
ms.assetid: F8D6680D-EFA7-4DED-B808-0E738A852641
ms.date: 04/30/2018
keywords: ["PEP_ACPI_PREPARE_DEVICE structure"]
ms.keywords: "*PPEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE, PEP_ACPI_PREPARE_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_PREPARE_DEVICE, PPEP_ACPI_PREPARE_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_PREPARE_DEVICE, kernel.pep_acpi_prepare_device, pepfx/PEP_ACPI_PREPARE_DEVICE, pepfx/PPEP_ACPI_PREPARE_DEVICE"
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
targetos: Windows
req.typenames: PEP_ACPI_PREPARE_DEVICE, *PPEP_ACPI_PREPARE_DEVICE
f1_keywords:
 - _PEP_ACPI_PREPARE_DEVICE
 - pep_x/_PEP_ACPI_PREPARE_DEVICE
 - PPEP_ACPI_PREPARE_DEVICE
 - pep_x/PPEP_ACPI_PREPARE_DEVICE
 - PEP_ACPI_PREPARE_DEVICE
 - pep_x/PEP_ACPI_PREPARE_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_PREPARE_DEVICE
---

# _PEP_ACPI_PREPARE_DEVICE structure


## -description

The <b>PEP_ACPI_PREPARE_DEVICE</b> structure indicates whether a platform extension plug-in (PEP) is prepared to provide ACPI services for the specified device.

## -struct-fields

### -field AcpiDeviceName

[in] A pointer to an <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a> structure that contains the fully qualified BIOS name for the device. This name specifies the path and name of the device in the ACPI namespace. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

### -field InputFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_PREPARE_DEVICE_INPUT_FLAG_NONE (0x0).

### -field DeviceAccepted

[out] Whether the PEP is prepared to provide ACPI services for the device. Set this member to TRUE if the PEP is prepared to be the sole provider of ACPI services for this device, and to FALSE if it is not.

### -field OutputFlags

[out] A set of output flags. No flags are currently defined for this member. Set this member to PEP_ACPI_PREPARE_DEVICE_OUTPUT_FLAG_NONE (0x0).

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_prepare_device">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a> notification. The <b>AcpiDeviceName</b> and <b>InputFlags</b> members of the structure contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>DeviceAccepted</b> and <b>OutputFlags</b> members contain output values that the PEP writes to the structure in response to the notification.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-string">ANSI_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_prepare_device">PEP_NOTIFY_ACPI_PREPARE_DEVICE</a>

