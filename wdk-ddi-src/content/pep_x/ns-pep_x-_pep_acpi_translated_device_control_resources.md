---
UID: NS:pep_x._PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
title: _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES (pep_x.h)
description: The PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.
old-location: kernel\pep_acpi_translated_device_control_resources.htm
tech.root: kernel
ms.assetid: 1274EF11-6A0D-4464-992D-4E27C981971F
ms.date: 04/30/2018
keywords: ["PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure"]
ms.keywords: "*PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure [Kernel-Mode Driver Architecture], _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, kernel.pep_acpi_translated_device_control_resources, pepfx/PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES"
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
req.typenames: PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES, *PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
f1_keywords:
 - _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
 - pep_x/_PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
 - PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
 - pep_x/PPEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
 - PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
 - pep_x/PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES
---

# _PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES structure


## -description

The <b>PEP_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</b> structure contains a list of translated power-control resources for the platform extension plug-in (PEP) to use.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.

### -field RequestFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_TDCR_FLAG_NONE (0x0).

### -field Status

[out] An NTSTATUS value that indicates the status of the resource translation. The PEP sets this member to STATUS_SUCCESS to indicate that the PEP successfully received the translated resources. Otherwise, the PEP sets this member to an appropriate error status code.

### -field TranslatedResourcesSize

### -field TranslatedResources

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a> structure that serves as the header for the resource list. The remainder of the resource list immediately follows this header.


#### - ResourceBufferSize

[in] The size in bytes of the input buffer that contains both this structure and the resource-list data that follows this structure.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_translated_device_control_resources">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a> notification to provide the PEP with a list of translated power control resources. The <b>RequestFlags</b>, <b>ResourceBufferSize</b>, and <b>TranslatedResources</b> members of the structure contain input values that the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) supplies when this notification is sent. The <b>Status</b> member contains an output value that the PEP writes to the structure in response to the notification.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_resource_list">CM_RESOURCE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_translated_device_control_resources">PEP_NOTIFY_ACPI_TRANSLATED_DEVICE_CONTROL_RESOURCES</a>

