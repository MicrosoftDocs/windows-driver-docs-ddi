---
UID: NS:hbapiwmi._HBAFCPBindingEntry2
title: HBAFCPBindingEntry2 (hbapiwmi.h)
description: Learn more about the HBAFCPBindingEntry2 structure.
old-location: storage\hbafcpbindingentry2.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["HBAFCPBindingEntry2 structure"]
ms.keywords: "*PHBAFCPBindingEntry2, HBAFCPBindingEntry2, HBAFCPBindingEntry2 structure [Storage Devices], PHBAFCPBindingEntry2, PHBAFCPBindingEntry2 structure pointer [Storage Devices], _HBAFCPBindingEntry2, hbapiwmi/HBAFCPBindingEntry2, hbapiwmi/PHBAFCPBindingEntry2, storage.hbafcpbindingentry2, structs-Fibre_b15c2291-b1fc-4f4f-9890-ddf50e3dee9e.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h, Hbaapi.h, Hbaapi.h
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
targetos: Windows
req.typenames: HBAFCPBindingEntry2, *PHBAFCPBindingEntry2
f1_keywords:
 - _HBAFCPBindingEntry2
 - hbapiwmi/_HBAFCPBindingEntry2
 - PHBAFCPBindingEntry2
 - hbapiwmi/PHBAFCPBindingEntry2
 - HBAFCPBindingEntry2
 - hbapiwmi/HBAFCPBindingEntry2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - _HBAFCPBindingEntry2
 - PHBAFCPBindingEntry2
 - HBAFCPBindingEntry2
---

# HBAFCPBindingEntry2 structure

## -description

The **HBAFCPBindingEntry2** structure defines a binding between the information that uniquely identifies a logical unit for the operating system and the fibre channel protocol (FCP) identifier for the logical unit.

## -struct-fields

### -field Type

Indicates the binding type. For a description of the values that this member can have, see the T11 committee's *Fibre Channel HBA API* specification.

| Value | Meaning |
| ----- | ------- |
| HBA_BIND_TO_D_ID | The target is identified by its fibre channel protocol (FCP) ID. The **Fcid** member of the [**HBAFCPID**](ns-hbapiwmi-_hbafcpid.md) structure contains this value. |
| HBA_BIND_TO_WWPN | The target is identified by its worldwide port name. The **PortWWN** member of the [**HBAFCPID**](ns-hbapiwmi-_hbafcpid.md) structure contains this value. |
| HBA_BIND_TO_WWNN | The fibre channel target device is identified by its worldwide node name. The **NodeWWN** member of the [**HBAFCPID**](ns-hbapiwmi-_hbafcpid.md) structure contains this value. |
| HBA_BIND_TO_LUID | The target is identified by its fibre channel logical unit ID. The **FcpLun** member of the [**HBAFCPID**](ns-hbapiwmi-_hbafcpid.md) structure contains this value. |
| HBA_BIND_TARGETS | The system should automatically generate target mappings from logical unit numbers to fibre channel protocol identifiers. |

For information about what needs to be included to use the symbols that represent the binding types, see the Headers section.

### -field FCPId

Contains a structure of type [**HBAFCPID**](ns-hbapiwmi-_hbafcpid.md) that contains the FCP identifier for the logical unit and information about the port to be queried for information about the device.

### -field Luid[256]

Contains the logical unit descriptor for the device that the operating system derives from SCSI inquiry data.

### -field ScsiId

Contains a structure of type [**HBAScsiID**](ns-hbapiwmi-_hbascsiid.md) that contains the information that uniquely identifies a logical unit for the operating system.

## -remarks

This structure is very similar to the [**HBAFCPBindingEntry**](ns-hbapiwmi-_hbafcpbindingentry.md) structure. The only difference is that **HBAFCPBindingEntry2** includes the number that the operating system generates for the logical unit.

The WMI tool suite generates a declaration of **HBAFCPBindingEntry2** automatically when it compiles the [HBAFCPBindingEntry WMI Class](/windows-hardware/drivers/storage/hbafcpbindingentry-wmi-class) that is defined in *hbaapi.mof*.

For an explanation of the fibre channel protocol (FCP), see the T11 committee's *dpANS Fibre Channel Protocol for SCSI* specification.

## -see-also

[**HBAFCPBindingEntry**](ns-hbapiwmi-_hbafcpbindingentry.md)

[HBAFCPBindingEntry2 WMI Class](/windows-hardware/drivers/storage/hbafcpbindingentry2-wmi-class)
