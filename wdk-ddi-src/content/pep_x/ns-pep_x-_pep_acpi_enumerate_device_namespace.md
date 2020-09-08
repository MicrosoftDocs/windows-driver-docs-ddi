---
UID: NS:pep_x._PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
title: _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE (pep_x.h)
description: The PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure contains an enumeration of the objects in the namespace of the device.
old-location: kernel\pep_acpi_enumerate_device_namespace.htm
tech.root: kernel
ms.assetid: 61315EFB-DEA7-4CF2-97D3-EACD223AFB50
ms.date: 04/30/2018
keywords: ["PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure"]
ms.keywords: "*PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, kernel.pep_acpi_enumerate_device_namespace, pepfx/PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, pepfx/PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE"
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
req.typenames: PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE, *PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
f1_keywords:
 - _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
 - pep_x/_PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
 - PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
 - pep_x/PPEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
 - PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
 - pep_x/PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE
---

# _PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE structure (pep_x.h)


## -description

The <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure contains an enumeration of the objects in the namespace of the device.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.

### -field RequestFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_EDN_FLAG_NONE (0x0).

### -field Status

[out] An NTSTATUS value that indicates the status of the requested device-namespace enumeration. Set this member to STATUS_SUCCESS if the PEP succeeds in enumerating the objects in the device namespace. Set to STATUS_BUFFER_TOO_SMALL if the input value in the <b>TotalBufferSize</b> member indicates that the allocated buffer is not large enough to contain the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure and <b>Objects</b> array.

### -field ObjectCount

[out] The number of elements in the <b>Objects</b> array.

### -field ObjectBufferSize

### -field Objects

[out] The first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_object_name_with_type">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structures that describe the objects in the ACPI namespace of the device. If this array contains more than one element, the additional array elements follow the end of the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure.


#### - TotalBufferSize

[in, out] On input, the total size, in bytes, of the buffer that the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) allocated for this structure and for any <b>Objects</b> array elements that follow the structure. If the input value of <b>TotalBufferSize</b> is not large enough to contain this structure and all the <b>Objects</b> array elements, the PEP overwrites the input value with the required size and sets the <b>Status</b> member to STATUS_BUFFER_TOO_SMALL. For more information, see Remarks.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_enumerate_device_namespace">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> notification. The <b>RequestFlags</b> and <b>TotalBufferSize</b> members contain input values supplied by PoFx when the notification is sent. The PEP may overwrite the <b>TotalBufferSize</b> input value with an output value if the input value is less than the required output buffer size. The <b>Status</b>, <b>ObjectCount</b>, and <b>Objects</b> members contain output values that the PEP writes to the structure.

If N is the number of objects listed in the ACPI namespace under this device, the PEP should verify that the storage allocated by PoFx for the <b>Objects</b> array is large enough to contain N array elements. If N > 1, the additional N–1 array elements follow the end of the <b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b> structure. The buffer size required to contain the structure and additional array elements is calculated as follows:

<b>sizeof</b>
<b>PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</b>
<b>sizeof</b>
<b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b>
If the input value specified in the <b>TotalBufferSize</b> member is less than the required size, the PEP overwrites the <b>TotalBufferSize</b> input value with the required size, and sets the <b>Status</b> member to STATUS_BUFFER_TOO_SMALL. In response, PoFx will allocate a buffer of the required size and send a second <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_enumerate_device_namespace">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> notification to the PEP for this device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_object_name_with_type">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_enumerate_device_namespace">PEP_NOTIFY_ACPI_ENUMERATE_DEVICE_NAMESPACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>

