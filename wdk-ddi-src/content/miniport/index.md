---
UID: NA:miniport
ms.assetid: a0a0b4a0-7bc0-3610-8f94-30f1e1e1cc06
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Miniport.h header



This header is used by Windows Driver Framework, Windows kernel, PCI, Display. For more information, see
- [Windows Driver Framework](../_wdf/index.md)
- [Windows kernel](../_kernel/index.md)
- [PCI](../_PCI/index.md)
- [Display](../_display/index.md)

Miniport.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [InterlockedAnd function](nf-miniport-interlockedand.md) | The InterlockedAnd macro atomically computes a bitwise AND operation. |
| [InterlockedCompareExchange function](nf-miniport-interlockedcompareexchange.md) | The InterlockedCompareExchange routine performs an atomic operation that compares the input value pointed to by Destination with the value of Comparand. |
| [InterlockedCompareExchangePointer function](nf-miniport-interlockedcompareexchangepointer.md) | The InterlockedCompareExchangePointer routine performs an atomic operation that compares the input pointer value pointed to by Destination with the pointer value Comparand. |
| [InterlockedDecrement function](nf-miniport-interlockeddecrement.md) | The InterlockedDecrement routine decrements a caller-supplied variable of type LONG as an atomic operation. |
| [InterlockedExchange function](nf-miniport-interlockedexchange.md) | The InterlockedExchange routine sets an integer variable to a given value as an atomic operation. |
| [InterlockedExchangeAdd function](nf-miniport-interlockedexchangeadd.md) | The InterlockedExchangeAdd routine adds a value to a given integer as an atomic operation and returns the original value of the given integer. |
| [InterlockedExchangePointer function](nf-miniport-interlockedexchangepointer.md) | The InterlockedExchangePointer routine performs an atomic operation that sets a pointer to a new value. |
| [InterlockedIncrement function](nf-miniport-interlockedincrement.md) | The InterlockedIncrement routine increments a caller-supplied variable as an atomic operation. |
| [InterlockedOr function](nf-miniport-interlockedor.md) | The InterlockedOr routine atomically computes a bitwise OR operation. |
| [InterlockedXor function](nf-miniport-interlockedxor.md) | The InterlockedOr routine atomically computes a bitwise exclusive OR operation. |
| [READ_PORT_BUFFER_UCHAR function](nf-miniport-read_port_buffer_uchar.md) | The READ_PORT_BUFFER_UCHAR routine reads a number of bytes from the specified port address into a buffer. |
| [READ_PORT_BUFFER_ULONG function](nf-miniport-read_port_buffer_ulong.md) | The READ_PORT_BUFFER_ULONG routine reads a number of ULONG values from the specified port address into a buffer. |
| [READ_PORT_BUFFER_USHORT function](nf-miniport-read_port_buffer_ushort.md) | The READ_PORT_BUFFER_USHORT routine reads a number of USHORT values from the specified port address into a buffer. |
| [READ_PORT_UCHAR function](nf-miniport-read_port_uchar.md) | The READ_PORT_UCHAR routine reads a byte from the specified port address. |
| [READ_PORT_ULONG function](nf-miniport-read_port_ulong.md) | The READ_PORT_ULONG routine reads a ULONG value from the specified port address. |
| [READ_PORT_USHORT function](nf-miniport-read_port_ushort.md) | The READ_PORT_USHORT routine reads a USHORT value from the specified port address. |
| [READ_REGISTER_BUFFER_UCHAR function](nf-miniport-read_register_buffer_uchar.md) | The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG function](nf-miniport-read_register_buffer_ulong.md) | The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG64 function](nf-miniport-read_register_buffer_ulong64.md) | The READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_USHORT function](nf-miniport-read_register_buffer_ushort.md) | The READ_REGISTER_BUFFER_USHORT routine reads a number of USHORT values from the specified register address into a buffer. |
| [READ_REGISTER_UCHAR function](nf-miniport-read_register_uchar.md) | The READ_REGISTER_UCHAR routine reads a byte from the specified register address. |
| [READ_REGISTER_ULONG function](nf-miniport-read_register_ulong.md) | The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address. |
| [READ_REGISTER_ULONG64 function](nf-miniport-read_register_ulong64.md) | The READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address. |
| [READ_REGISTER_USHORT function](nf-miniport-read_register_ushort.md) | The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address. |
| [WRITE_PORT_BUFFER_UCHAR function](nf-miniport-write_port_buffer_uchar.md) | The WRITE_PORT_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified port. |
| [WRITE_PORT_BUFFER_ULONG function](nf-miniport-write_port_buffer_ulong.md) | The WRITE_PORT_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified port address. |
| [WRITE_PORT_BUFFER_USHORT function](nf-miniport-write_port_buffer_ushort.md) | The WRITE_PORT_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified port address. |
| [WRITE_PORT_UCHAR function](nf-miniport-write_port_uchar.md) | The WRITE_PORT_UCHAR routine writes a byte to the specified port address. |
| [WRITE_PORT_ULONG function](nf-miniport-write_port_ulong.md) | The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address. |
| [WRITE_PORT_USHORT function](nf-miniport-write_port_ushort.md) | The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address. |
| [WRITE_REGISTER_BUFFER_UCHAR function](nf-miniport-write_register_buffer_uchar.md) | The WRITE_REGISTER_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG function](nf-miniport-write_register_buffer_ulong.md) | The WRITE_REGISTER_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG64 function](nf-miniport-write_register_buffer_ulong64.md) | The WRITE_REGISTER_BUFFER_ULONG64 function writes a number of ULONG64 values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_USHORT function](nf-miniport-write_register_buffer_ushort.md) | The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register. |
| [WRITE_REGISTER_UCHAR function](nf-miniport-write_register_uchar.md) | The WRITE_REGISTER_UCHAR routine writes a byte to the specified address. |
| [WRITE_REGISTER_ULONG function](nf-miniport-write_register_ulong.md) | The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address. |
| [WRITE_REGISTER_ULONG64 function](nf-miniport-write_register_ulong64.md) | The WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address. |
| [WRITE_REGISTER_USHORT function](nf-miniport-write_register_ushort.md) | The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PINTERFACE_DEREFERENCE callback](nc-miniport-pinterface_dereference.md) | The InterfaceDereference routine decrements the reference count on a driver-defined interface. |
| [PINTERFACE_REFERENCE callback](nc-miniport-pinterface_reference.md) | The InterfaceReference routine increments the reference count on a driver-defined interface. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [PCI_X_CAPABILITY structure](ns-miniport-pci_x_capability.md) | The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the PCI-X Addendum to the PCI Local Bus Specification. |
| [_CM_EISA_FUNCTION_INFORMATION structure](ns-miniport-_cm_eisa_function_information.md) | The CM_EISA_FUNCTION_INFORMATION structure defines detailed EISA configuration information returned by HalGetBusData for the input BusDataType EisaConfiguration, or by HalGetBusDataByOffset for the input BusDataType EisaConfiguration and the Offset zero, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_EISA_SLOT_INFORMATION structure](ns-miniport-_cm_eisa_slot_information.md) | The CM_EISA_SLOT_INFORMATION structure defines EISA configuration header information returned by HalGetBusData for the input BusDataType = EisaConfiguration, or by HalGetBusDataByOffset for the inputs BusDataType = EisaConfiguration and Offset = 0, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_MCA_POS_DATA structure](ns-miniport-_cm_mca_pos_data.md) | The CM_MCA_POS_DATA structure is obsolete. It defines IBM-compatible MCA POS configuration information for a slot. |
| [_EMULATOR_ACCESS_ENTRY structure](ns-miniport-_emulator_access_entry.md) | The EMULATOR_ACCESS_ENTRY structure specifies an element in the EmulatorAccessEntries array set up in the VIDEO_PORT_CONFIG_INFO structure by drivers of VGA-compatible (SVGA) adapters on x86-based NT-based operating system platforms. |
| [_GROUP_AFFINITY structure](ns-miniport-_group_affinity.md) | The GROUP_AFFINITY structure specifies a group number and the processor affinity within that group. |
| [_INTERFACE structure](ns-miniport-_interface.md) | The INTERFACE structure describes an interface that is exported by a driver for use by other drivers. |
| [_IO_RESOURCE_DESCRIPTOR structure](ns-miniport-_io_resource_descriptor.md) | The IO_RESOURCE_DESCRIPTOR structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of IO_RESOURCE_DESCRIPTOR structures is contained within each IO_RESOURCE_LIST structure. |
| [_IO_RESOURCE_LIST structure](ns-miniport-_io_resource_list.md) | The IO_RESOURCE_LIST structure describes a range of raw hardware resources, of various types, that can be used by a device. |
| [_IO_RESOURCE_REQUIREMENTS_LIST structure](ns-miniport-_io_resource_requirements_list.md) | The IO_RESOURCE_REQUIREMENTS_LIST structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device. |
| [_PCI_CAPABILITIES_HEADER structure](ns-miniport-_pci_capabilities_header.md) | The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure. |
| [_PCI_COMMON_CONFIG structure](ns-miniport-_pci_common_config.md) | The PCI_COMMON_CONFIG structure is obsolete. |
| [_PCI_EXPRESS_AER_CAPABILITIES structure](ns-miniport-_pci_express_aer_capabilities.md) | The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_AER_CAPABILITY structure](ns-miniport-_pci_express_aer_capability.md) | The PCI_EXPRESS_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure. |
| [_PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure](ns-miniport-_pci_express_bridge_aer_capability.md) | The PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a PCIe bridge device. |
| [_PCI_EXPRESS_CAPABILITIES_REGISTER structure](ns-miniport-_pci_express_capabilities_register.md) | The PCI_EXPRESS_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) capabilities register of a PCIe capability structure. |
| [_PCI_EXPRESS_CAPABILITY structure](ns-miniport-_pci_express_capability.md) | The PCI_EXPRESS_CAPABILITY structure describes a PCI Express (PCIe) capability structure. |
| [_PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure](ns-miniport-_pci_express_correctable_error_mask.md) | The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure](ns-miniport-_pci_express_correctable_error_status.md) | The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER structure](ns-miniport-_pci_express_device_capabilities_register.md) | The PCI_EXPRESS_DEVICE_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) device capabilities register of a PCIe capability structure. |
| [_PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure](ns-miniport-_pci_express_device_control_register.md) | The PCI_EXPRESS_DEVICE_CONTROL_REGISTER structure describes a PCI Express (PCIe) device control register of a PCIe capability structure. |
| [_PCI_EXPRESS_DEVICE_STATUS_REGISTER structure](ns-miniport-_pci_express_device_status_register.md) | The PCI_EXPRESS_DEVICE_STATUS_REGISTER structure describes a PCI Express (PCIe) device status register of a PCIe capability structure. |
| [_PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure](ns-miniport-_pci_express_enhanced_capability_header.md) | The PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure describes the header for a PCI Express (PCIe) extended capability structure. |
| [_PCI_EXPRESS_ERROR_SOURCE_ID structure](ns-miniport-_pci_express_error_source_id.md) | The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register. |
| [_PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure](ns-miniport-_pci_express_link_capabilities_register.md) | The PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) link capabilities register of a PCIe capability structure. |
| [_PCI_EXPRESS_LINK_CONTROL_REGISTER structure](ns-miniport-_pci_express_link_control_register.md) | The PCI_EXPRESS_LINK_CONTROL_REGISTER structure describes a PCI Express (PCIe) link control register of a PCIe capability structure. |
| [_PCI_EXPRESS_LINK_STATUS_REGISTER structure](ns-miniport-_pci_express_link_status_register.md) | The PCI_EXPRESS_LINK_STATUS_REGISTER structure describes a PCI Express (PCIe) link status register of a PCIe capability structure. |
| [_PCI_EXPRESS_PME_REQUESTOR_ID structure](ns-miniport-_pci_express_pme_requestor_id.md) | The PCI_EXPRESS_PME_REQUESTOR_ID structure describes the identifier of the requester of a power management event (PME). |
| [_PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure](ns-miniport-_pci_express_rootport_aer_capability.md) | The PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a root port or a root complex event collector. |
| [_PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure](ns-miniport-_pci_express_root_capabilities_register.md) | The PCI_EXPRESS_ROOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) root capabilities register of a PCIe capability structure. |
| [_PCI_EXPRESS_ROOT_CONTROL_REGISTER structure](ns-miniport-_pci_express_root_control_register.md) | The PCI_EXPRESS_ROOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) root control register of a PCIe capability structure. |
| [_PCI_EXPRESS_ROOT_ERROR_COMMAND structure](ns-miniport-_pci_express_root_error_command.md) | The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_ROOT_ERROR_STATUS structure](ns-miniport-_pci_express_root_error_status.md) | The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_ROOT_STATUS_REGISTER structure](ns-miniport-_pci_express_root_status_register.md) | The PCI_EXPRESS_ROOT_STATUS_REGISTER structure describes a PCI Express (PCIe) root status register of a PCIe capability structure. |
| [_PCI_EXPRESS_SEC_AER_CAPABILITIES structure](ns-miniport-_pci_express_sec_aer_capabilities.md) | The PCI_EXPRESS_SEC_AER_CAPABILITIES structure describes a PCI Express (PCIe) secondary error capabilities and control register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure](ns-miniport-_pci_express_sec_uncorrectable_error_mask.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure](ns-miniport-_pci_express_sec_uncorrectable_error_severity.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) secondary uncorrectable error severity register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure](ns-miniport-_pci_express_sec_uncorrectable_error_status.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure](ns-miniport-_pci_express_serial_number_capability.md) | The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device. |
| [_PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER structure](ns-miniport-_pci_express_slot_capabilities_register.md) | The PCI_EXPRESS_SLOT_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) slot capabilities register of a PCIe capability structure. |
| [_PCI_EXPRESS_SLOT_CONTROL_REGISTER structure](ns-miniport-_pci_express_slot_control_register.md) | The PCI_EXPRESS_SLOT_CONTROL_REGISTER structure describes a PCI Express (PCIe) slot control register of a PCIe capability structure. |
| [_PCI_EXPRESS_SLOT_STATUS_REGISTER structure](ns-miniport-_pci_express_slot_status_register.md) | The PCI_EXPRESS_SLOT_STATUS_REGISTER structure describes a PCI Express (PCIe) slot status register of a PCIe capability structure. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure](ns-miniport-_pci_express_uncorrectable_error_mask.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure](ns-miniport-_pci_express_uncorrectable_error_severity.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure](ns-miniport-_pci_express_uncorrectable_error_status.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_PMC structure](ns-miniport-_pci_pmc.md) | The PCI_PMC structure is used to report the contents of the power management capabilities register. |
| [_PCI_PMCSR structure](ns-miniport-_pci_pmcsr.md) | The PCI_PMCSR structure is used to report the contents of the device's power management control status register. |
| [_PCI_PMCSR_BSE structure](ns-miniport-_pci_pmcsr_bse.md) | The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions. |
| [_PCI_PM_CAPABILITY structure](ns-miniport-_pci_pm_capability.md) | The PCI_PM_CAPABILITY structure reports the power management capabilities of the device. |
| [_PCI_SLOT_NUMBER structure](ns-miniport-_pci_slot_number.md) | The PCI_SLOT_NUMBER structure is obsolete. |
| [_PROCESSOR_NUMBER structure](ns-miniport-_processor_number.md) | The PROCESSOR_NUMBER structure identifies a processor by its group number and group-relative processor number. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_BUS_DATA_TYPE enumeration](ne-miniport-_bus_data_type.md) | The BUS_DATA_TYPE enumeration indicates the type of bus configuration space. |
| [_INTERFACE_TYPE enumeration](ne-miniport-_interface_type.md) | The INTERFACE_TYPE enumeration indicates the bus type. |
| [_IRQ_DEVICE_POLICY enumeration](ne-miniport-_irq_device_policy.md) | The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors. |
| [_IRQ_PRIORITY enumeration](ne-miniport-_irq_priority.md) | The IRQ_PRIORITY enumeration type indicates the priority the system should give to servicing a device's interrupts. |
| [_KINTERRUPT_MODE enumeration](ne-miniport-_kinterrupt_mode.md) | The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered. |
| [_KINTERRUPT_POLARITY enumeration](ne-miniport-_kinterrupt_polarity.md) | The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line. |
| [_MEMORY_CACHING_TYPE enumeration](ne-miniport-_memory_caching_type.md) | The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [FIELD_OFFSET macro](nf-miniport-field_offset.md) | The FIELD_OFFSET macro returns the byte offset of a named field in a known structure type. |
