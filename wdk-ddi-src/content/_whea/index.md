---
UID: TP:whea
ms.assetid: 069ae67e-570f-3fce-99d4-d889f7094ff1
ms.author: windowsdriverdev
ms.date: 01/18/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Windows Hardware Error Architecture (WHEA)


Overview of the Windows Hardware Error Architecture (WHEA) technology.

To develop Windows Hardware Error Architecture (WHEA), you need these headers:

 * [ntddk.h](..\ntddk\index.md)

For the programming guide, see [Windows Hardware Error Architecture (WHEA)](https://docs.microsoft.com/en-us/windows-hardware/drivers/whea).

## Functions

| Title   | Description   |
| ---- |:---- |
| [PshedAllocateMemory function](..\ntddk\nf-ntddk-pshedallocatememory.md) | The PshedAllocateMemory function allocates a block of memory from the nonpaged pool. |
| [PshedFreeMemory function](..\ntddk\nf-ntddk-pshedfreememory.md) | The PshedFreeMemory function frees a block of memory that was previously allocated by calling the PshedAllocateMemory function. |
| [PshedIsSystemWheaEnabled function](..\ntddk\nf-ntddk-pshedissystemwheaenabled.md) | The PshedIsSystemWheaEnabled function returns a Boolean value that indicates whether the system is WHEA-enabled. |
| [PshedRegisterPlugin function](..\ntddk\nf-ntddk-pshedregisterplugin.md) | The PshedRegisterPlugin function registers a PSHED plug-in with the PSHED. |
| [PshedSynchronizeExecution function](..\ntddk\nf-ntddk-pshedsynchronizeexecution.md) | The PshedSynchronizeExecution function synchronizes the execution of a given function with the hardware error processing for an error source. |
| [WheaFindErrorRecordSection function](..\ntddk\nf-ntddk-wheafinderrorrecordsection.md) | The WheaFindErrorRecordSection function searches for a specified Windows Hardware Error Architecture (WHEA) error record section within a WHEA error record. The error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure. |
| [WheaFindNextErrorRecordSection function](..\ntddk\nf-ntddk-wheafindnexterrorrecordsection.md) | The WheaFindNextErrorRecordSection function allows a caller to iteratively examine the WHEA error record sections within a WHEA error record. Each error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure. |
| [WheaGetErrPacketFromErrRecord function](..\ntddk\nf-ntddk-wheageterrpacketfromerrrecord.md) | The WheaGetErrPacketFromErrRecord function returns a pointer to the hardware error packet that is contained within a WHEA error record. The hardware error packet is formatted as a WHEA_ERROR_PACKET structure. |
| [WheaIsValidErrorRecordSignature function](..\ntddk\nf-ntddk-wheaisvaliderrorrecordsignature.md) | The WheaIsValidErrorRecordSignature function verifies whether a WHEA error record is valid. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PSHED_PI_ATTEMPT_ERROR_RECOVERY callback](..\ntddk\nc-ntddk-pshed_pi_attempt_error_recovery.md) | A PSHED plug-in's AttemptRecovery callback function attempts to recover from a recoverable hardware error. |
| [PSHED_PI_CLEAR_ERROR_RECORD callback](..\ntddk\nc-ntddk-pshed_pi_clear_error_record.md) | A PSHED plug-in's ClearErrorRecord callback function clears the specified error record from the system's persistent data storage. |
| [PSHED_PI_CLEAR_ERROR_STATUS callback](..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md) | A PSHED plug-in's ClearErrorStatus callback function clears any platform-specific error status registers for a corrected hardware error condition. |
| [PSHED_PI_DISABLE_ERROR_SOURCE callback](..\ntddk\nc-ntddk-pshed_pi_disable_error_source.md) | A PSHED plug-in's DisableErrorSource callback function disables an error source. |
| [PSHED_PI_ENABLE_ERROR_SOURCE callback](..\ntddk\nc-ntddk-pshed_pi_enable_error_source.md) | A PSHED plug-in's EnableErrorSource callback function enables an error source. |
| [PSHED_PI_FINALIZE_ERROR_RECORD callback](..\ntddk\nc-ntddk-pshed_pi_finalize_error_record.md) | A PSHED plug-in's FinalizeErrorRecord callback function adds supplementary error record sections to an error record that more fully describe the error condition. |
| [PSHED_PI_GET_ALL_ERROR_SOURCES callback](..\ntddk\nc-ntddk-pshed_pi_get_all_error_sources.md) | A PSHED plug-in's GetAllErrorSources callback function returns a list of error source descriptor structures that represents all of the error sources that are implemented by the hardware platform. |
| [PSHED_PI_GET_ERROR_SOURCE_INFO callback](..\ntddk\nc-ntddk-pshed_pi_get_error_source_info.md) | A PSHED plug-in's GetErrorSourceInfo callback function returns an error source descriptor structure that represents a particular error source that is implemented by the hardware platform. |
| [PSHED_PI_GET_INJECTION_CAPABILITIES callback](..\ntddk\nc-ntddk-pshed_pi_get_injection_capabilities.md) | A PSHED plug-in's GetInjectionCapabilities callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform. |
| [PSHED_PI_INJECT_ERROR callback](..\ntddk\nc-ntddk-pshed_pi_inject_error.md) | A PSHED plug-in's InjectError callback function injects an error into the hardware platform. |
| [PSHED_PI_READ_ERROR_RECORD callback](..\ntddk\nc-ntddk-pshed_pi_read_error_record.md) | A PSHED plug-in's ReadErrorRecord callback function reads an error record from the system's persistent data storage. |
| [PSHED_PI_RETRIEVE_ERROR_INFO callback](..\ntddk\nc-ntddk-pshed_pi_retrieve_error_info.md) | A PSHED plug-in's RetrieveErrorInfo callback function retrieves platform-specific error information about a hardware error that has occurred. |
| [PSHED_PI_SET_ERROR_SOURCE_INFO callback](..\ntddk\nc-ntddk-pshed_pi_set_error_source_info.md) | A PSHED plug-in's SetErrorSourceInfo callback function configures an error source. |
| [PSHED_PI_WRITE_ERROR_RECORD callback](..\ntddk\nc-ntddk-pshed_pi_write_error_record.md) | A PSHED plug-in's WriteErrorRecord callback function writes an error record to the system's persistent data storage. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [WHEA_XPF_PROCESSOR_ERROR_SECTION structure](..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md) | The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture. |
| [WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-whea_xpf_processor_error_section_validbits.md) | The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member. |
| [_SOC_SUBSYSTEM_FAILURE_DETAILS structure](..\ntddk\ns-ntddk-_soc_subsystem_failure_details.md) | The SOC_SUBSYSTEM_FAILURE_DETAILS structure holds information related to a System on a Chip (SoC) bug code. |
| [_WHEA_AER_BRIDGE_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_aer_bridge_descriptor.md) | The WHEA_AER_BRIDGE_DESCRIPTOR structure describes a PCI Express (PCIe) bridge error source. |
| [_WHEA_AER_ENDPOINT_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_aer_endpoint_descriptor.md) | The WHEA_AER_ENDPOINT_DESCRIPTOR structure describes a PCI Express (PCIe) endpoint error source. |
| [_WHEA_AER_ROOTPORT_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_aer_rootport_descriptor.md) | The WHEA_AER_ROOTPORT_DESCRIPTOR structure describes a PCI Express (PCIe) root port error source. |
| [_WHEA_ERROR_INJECTION_CAPABILITIES structure](..\ntddk\ns-ntddk-_whea_error_injection_capabilities.md) | The WHEA_ERROR_INJECTION_CAPABILITIES union describes the types of hardware errors that can be injected into a hardware platform. |
| [_WHEA_ERROR_PACKET_FLAGS structure](..\ntddk\ns-ntddk-_whea_error_packet_flags.md) | The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a WHEA_ERROR_PACKET structure. |
| [_WHEA_ERROR_PACKET_V1 structure](..\ntddk\ns-ntddk-_whea_error_packet_v1.md) | The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1. |
| [_WHEA_ERROR_PACKET_V2 structure](..\ntddk\ns-ntddk-_whea_error_packet_v2.md) | The WHEA_ERROR_PACKET_V2 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V2 structure is supported in Windows 7 and later versions of Windows. |
| [_WHEA_ERROR_RECORD structure](..\ntddk\ns-ntddk-_whea_error_record.md) | The WHEA_ERROR_RECORD structure describes an error record that contains error information about a hardware error condition that occurred. |
| [_WHEA_ERROR_RECORD_HEADER structure](..\ntddk\ns-ntddk-_whea_error_record_header.md) | The WHEA_ERROR_RECORD_HEADER structure describes general information about a hardware error condition. |
| [_WHEA_ERROR_RECORD_HEADER_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_error_record_header_validbits.md) | The WHEA_ERROR_RECORD_HEADER_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_HEADER structure contain valid data. |
| [_WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md) | The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an error record. |
| [_WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_error_record_section_descriptor_validbits.md) | The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contain valid data. |
| [_WHEA_ERROR_SOURCE_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_error_source_descriptor.md) | The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source. |
| [_WHEA_ERROR_STATUS structure](..\ntddk\ns-ntddk-_whea_error_status.md) | The WHEA_ERROR_STATUS union describes generic error codes that are abstracted from the data contained in implementation-specific error registers. |
| [_WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure](..\ntddk\ns-ntddk-_whea_firmware_error_record_reference.md) | The WHEA_FIRMWARE_ERROR_RECORD_REFERENCE structure describes a reference to a firmware error record that is specific to the Itanium processor architecture. |
| [_WHEA_GENERIC_ERROR structure](..\ntddk\ns-ntddk-_whea_generic_error.md) | The WHEA_GENERIC_ERROR structure describes error status data for a generic error source. |
| [_WHEA_GENERIC_ERROR_BLOCKSTATUS structure](..\ntddk\ns-ntddk-_whea_generic_error_blockstatus.md) | The WHEA_GENERIC_ERROR_BLOCKSTATUS union indicates what kind of error data is reported in a generic error status block. |
| [_WHEA_GENERIC_ERROR_DATA_ENTRY_V2 structure](..\ntddk\ns-ntddk-_whea_generic_error_data_entry_v2.md) | The WHEA_GENERIC_ERROR_DATA_ENTRY structure describes an error data section in a generic error status block. |
| [_WHEA_GENERIC_ERROR_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_generic_error_descriptor.md) | The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source. |
| [_WHEA_IPF_CMC_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_ipf_cmc_descriptor.md) | The WHEA_IPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an Itanium processor. |
| [_WHEA_IPF_CPE_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_ipf_cpe_descriptor.md) | The WHEA_IPF_CPE_DESCRIPTOR structure describes a corrected platform error (CPE) error source for an Itanium processor. |
| [_WHEA_IPF_MCA_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_ipf_mca_descriptor.md) | The WHEA_IPF_MCA_DESCRIPTOR structure describes a machine check abort (MCA) error source for an Itanium processor. |
| [_WHEA_MEMORY_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_memory_error_section.md) | The WHEA_MEMORY_ERROR_SECTION structure describes platform memory error data. |
| [_WHEA_MEMORY_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_memory_error_section_validbits.md) | The WHEA_MEMORY_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_MEMORY_ERROR_SECTION structure contain valid data. |
| [_WHEA_NMI_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_nmi_error_section.md) | The WHEA_NMI_ERROR_SECTION structure describes nonmaskable interrupt (NMI) error data. |
| [_WHEA_NOTIFICATION_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_notification_descriptor.md) | The WHEA_NOTIFICATION_DESCRIPTOR structure describes the notification mechanism that is used by an error source. |
| [_WHEA_PCIEXPRESS_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md) | The WHEA_PCIEXPRESS_ERROR_SECTION structure describes PCI Express (PCIe) error data. |
| [_WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_pciexpress_error_section_validbits.md) | The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIEXPRESS_ERROR_SECTION structure contain valid data. |
| [_WHEA_PCIXBUS_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md) | The WHEA_PCIXBUS_ERROR_SECTION structure describes PCI or PCI-X bus error data. |
| [_WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_pcixbus_error_section_validbits.md) | The WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIXBUS_ERROR_SECTION structure contain valid data. |
| [_WHEA_PCIXDEVICE_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md) | The WHEA_PCIXDEVICE_ERROR_SECTION structure describes PCI or PCI-X device error data. |
| [_WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_pcixdevice_error_section_validbits.md) | The WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIXDEVICE_ERROR_SECTION structure contain valid data. |
| [_WHEA_PCI_SLOT_NUMBER structure](..\ntddk\ns-ntddk-_whea_pci_slot_number.md) | The WHEA_PCI_SLOT_NUMBER structure describes a logical PCI slot. |
| [_WHEA_PERSISTENCE_INFO structure](..\ntddk\ns-ntddk-_whea_persistence_info.md) | The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record. |
| [_WHEA_PROCESSOR_FAMILY_INFO structure](..\ntddk\ns-ntddk-_whea_processor_family_info.md) | The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor. |
| [_WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md) | Describes processor error data that is not specific to a particular processor architecture. |
| [_WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_processor_generic_error_section_validbits.md) | The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contain valid data. |
| [_WHEA_PSHED_PLUGIN_CALLBACKS structure](..\ntddk\ns-ntddk-_whea_pshed_plugin_callbacks.md) | The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in. |
| [_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure](..\ntddk\ns-ntddk-_whea_pshed_plugin_registration_packet.md) | The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure describes the data required for registering a PSHED plug-in with the PSHED. |
| [_WHEA_REVISION structure](..\ntddk\ns-ntddk-_whea_revision.md) | The WHEA_REVISION union describes the revision of the error record data structures. |
| [_WHEA_TIMESTAMP structure](..\ntddk\ns-ntddk-_whea_timestamp.md) | The WHEA_TIMESTAMP union describes the time that an error was reported to the operating system. |
| [_WHEA_X64_REGISTER_STATE structure](..\ntddk\ns-ntddk-_whea_x64_register_state.md) | The WHEA_X64_REGISTER_STATE structure describes the state of an x64 processor's registers. |
| [_WHEA_X86_REGISTER_STATE structure](..\ntddk\ns-ntddk-_whea_x86_register_state.md) | The WHEA_X86_REGISTER_STATE structure describes the state of an x86 processor's registers. |
| [_WHEA_XPF_BUS_CHECK structure](..\ntddk\ns-ntddk-_whea_xpf_bus_check.md) | The WHEA_XPF_BUS_CHECK union describes bus error information for an x86 or x64 processor. |
| [_WHEA_XPF_CACHE_CHECK structure](..\ntddk\ns-ntddk-_whea_xpf_cache_check.md) | The WHEA_XPF_CACHE_CHECK union describes cache error information for an x86 or x64 processor. |
| [_WHEA_XPF_CMC_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_xpf_cmc_descriptor.md) | The WHEA_XPF_CMC_DESCRIPTOR structure describes a corrected machine check (CMC) error source for an x86 or x64 processor. |
| [_WHEA_XPF_CONTEXT_INFO structure](..\ntddk\ns-ntddk-_whea_xpf_context_info.md) | The WHEA_XPF_CONTEXT_INFO structure describes processor context information for an x86 or x64 processor. |
| [_WHEA_XPF_MCE_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_xpf_mce_descriptor.md) | The WHEA_XPF_MCE_DESCRIPTOR structure describes a machine check exception (MCE) error source for an x86 or x64 processor. |
| [_WHEA_XPF_MC_BANK_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_xpf_mc_bank_descriptor.md) | The WHEA_XPF_MC_BANK_DESCRIPTOR structure describes a bank of machine check registers for an x86 or x64 processor. |
| [_WHEA_XPF_MS_CHECK structure](..\ntddk\ns-ntddk-_whea_xpf_ms_check.md) | The WHEA_XPF_MS_CHECK union describes microarchitecture-specific error information for an x86 or x64 processor. |
| [_WHEA_XPF_NMI_DESCRIPTOR structure](..\ntddk\ns-ntddk-_whea_xpf_nmi_descriptor.md) | The WHEA_XPF_NMI_DESCRIPTOR structure describes a nonmaskable interrupt (NMI) error source for an x86 or x64 processor. |
| [_WHEA_XPF_PROCESSOR_ERROR_SECTION structure](..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md) | The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture. |
| [_WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_xpf_processor_error_section_validbits.md) | The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member. |
| [_WHEA_XPF_PROCINFO structure](..\ntddk\ns-ntddk-_whea_xpf_procinfo.md) | The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures. |
| [_WHEA_XPF_PROCINFO_VALIDBITS structure](..\ntddk\ns-ntddk-_whea_xpf_procinfo_validbits.md) | The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a WHEA_XPF_PROCINFO structure contain valid data. |
| [_WHEA_XPF_TLB_CHECK structure](..\ntddk\ns-ntddk-_whea_xpf_tlb_check.md) | The WHEA_XPF_TLB_CHECK union describes translation lookaside buffer (TLB) error information for an x86 or x64 processor. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_SOC_SUBSYSTEM_TYPE enumeration](..\ntddk\ne-ntddk-_soc_subsystem_type.md) | The SOC_SYBSYSTEM_TYPE enumeration defines different types of System on a Chip (SoC) subsystems. |
| [_WHEA_ERROR_PACKET_DATA_FORMAT enumeration](..\ntddk\ne-ntddk-_whea_error_packet_data_format.md) | The WHEA_ERROR_PACKET_DATA_FORMAT enumeration defines the raw hardware error data format in a hardware error packet. |
| [_WHEA_ERROR_SEVERITY enumeration](..\ntddk\ne-ntddk-_whea_error_severity.md) | The WHEA_ERROR_SEVERITY enumeration defines the possible severity levels of a hardware error condition. |
| [_WHEA_ERROR_SOURCE_STATE enumeration](..\ntddk\ne-ntddk-_whea_error_source_state.md) | The WHEA_ERROR_SOURCE_STATE enumeration defines the different runtime states for an error source. |
| [_WHEA_ERROR_SOURCE_TYPE enumeration](..\ntddk\ne-ntddk-_whea_error_source_type.md) | The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors. |
| [_WHEA_ERROR_TYPE enumeration](..\ntddk\ne-ntddk-_whea_error_type.md) | The WHEA_ERROR_TYPE enumeration defines the different types of hardware components that can report a hardware error. |
| [_WHEA_RAW_DATA_FORMAT enumeration](..\ntddk\ne-ntddk-_whea_raw_data_format.md) | The WHEA_RAW_DATA_FORMAT enumeration defines the possible formats that raw hardware error data can be encoded in a hardware error packet. |
