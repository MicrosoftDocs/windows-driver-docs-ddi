---
UID: NS:ntddk._PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
tech.root: kernel
title: PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER union.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER, *PPCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - PPCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - ntddk/_PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - PPCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - ntddk/PPCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
 - ntddk/PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
dev_langs:
 - c++
helpviewer_keywords:
 - _PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER
---

## -description

The **PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER** structure describes a PCI Express (PCIe) link capabilities 2 register of a PCIe capability structure. This is an extension of the PCIe link capabilities register.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.Rsvd0

Reserved.

### -field DUMMYSTRUCTNAME.SupportedLinkSpeedsVector

Indicates the supported link speeds of the PCIe link. For each bit position, a value of 1b indicates that the corresponding link speed is supported; otherwise, that speed is not supported. Note that this field is preferred as the source of truth over the [MaximumLinkSpeed](ns-ntddk-_pci_express_link_capabilities_register.md#-field-DUMMYSTRUCTNAME.MaximumLinkSpeed) field.

Bit definitions within this field with the corresponding link speed are:

<table>
<tr>
<th>Bit Position</th>
<th>Supported Link Speed</th>
</tr>
<tr>
<td><b>0</b></td>
<td>2.5 GT/s</td>
</tr>
<tr>
<td><b>1</b></td>
<td>5.0 GT/s</td>
</tr>
<tr>
<td><b>2</b></td>
<td>8.0 GT/s</td>
</tr>
<tr>
<td><b>3</b></td>
<td>16.0 GT/s</td>
</tr>
<tr>
<td><b>4</b></td>
<td>32.0 GT/s</td>
</tr>
<tr>
<td><b>All other bit positions</b></td>
<td>Reserved</td>
</tr>
</table>


### -field DUMMYSTRUCTNAME.Rsvd8_31

Reserved.

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER** structure.

## -remarks

A **PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md)

[PCI_EXPRESS_LINK_CAPABILITIES_REGISTER](ns-ntddk-_pci_express_link_capabilities_register.md)
