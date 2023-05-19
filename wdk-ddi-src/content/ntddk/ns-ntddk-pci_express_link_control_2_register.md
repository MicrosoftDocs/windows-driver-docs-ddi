---
UID: NS:ntddk._PCI_EXPRESS_LINK_CONTROL_2_REGISTER
tech.root: kernel
title: PCI_EXPRESS_LINK_CONTROL_2_REGISTER (ntddk.h)
ms.date: 03/28/2022
targetos: Windows
description: This topic describes the PCI_EXPRESS_LINK_CONTROL_2_REGISTER union.
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
req.typenames: PCI_EXPRESS_LINK_CONTROL_2_REGISTER, *PPCI_EXPRESS_LINK_CONTROL_2_REGISTER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - PPCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - PCI_EXPRESS_LINK_CONTROL_2_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - ntddk/_PCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - PPCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - ntddk/PPCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - PCI_EXPRESS_LINK_CONTROL_2_REGISTER
 - ntddk/PCI_EXPRESS_LINK_CONTROL_2_REGISTER
dev_langs:
 - c++
helpviewer_keywords:
 - _PCI_EXPRESS_LINK_CONTROL_2_REGISTER
---

## -description

The **PCI_EXPRESS_LINK_CONTROL_2_REGISTER** structure describes a PCI Express (PCIe) link control 2 register of a PCIe capability structure. This is an extension of the PCIe link control register.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field DUMMYSTRUCTNAME.TargetLinkSpeed

For Downstream Ports, this field sets an upper limit on a PCIe link's operational speed by restricting the values advertised by the Upstream component in its training sequences.
The encoded value specifies a bit location in the Supported Link Speeds Vector (in the Link Capabilities 2 Register) corresponding to the desired operational link speed.

Defined encodings are:

<table>
<tr>
<th>Value (binary)</th>
<th>Supported Link Speeds Vector field bit position</th>
<th>Link Speed</th>
</tr>
<tr>
<td><b>0001b</b></td>
<td>0</td>
<td>2.5 GT/s</td>
</tr>
<tr>
<td><b>0010b</b></td>
<td>1</td>
<td>5.0 GT/s</td>
</tr>
<tr>
<td><b>0011b</b></td>
<td>2</td>
<td>8.0 GT/s</td>
</tr>
<tr>
<td><b>0100b</b></td>
<td>3</td>
<td>16.0 GT/s</td>
</tr>
<tr>
<td><b>0101b</b></td>
<td>4</td>
<td>32.0 GT/s</td>
</tr>
<tr>
<td><b>All other values</b></td>
<td>Reserved</td>
<td>Reserved</td>
</tr>
</table>

### -field DUMMYSTRUCTNAME.Rsvd4_15

Reserved.

### -field AsUSHORT

A **USHORT** representation of the contents of the **PCI_EXPRESS_LINK_CONTROL_2_REGISTER** structure.

## -remarks

A **PCI_EXPRESS_LINK_CONTROL_2_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md)

[PCI_EXPRESS_LINK_CONTROL_REGISTER](ns-ntddk-pci_express_link_control_register.md)

