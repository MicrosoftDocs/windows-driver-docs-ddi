---
UID: NS:ntddk._WHEA_ERROR_SOURCE_DESCRIPTOR
title: _WHEA_ERROR_SOURCE_DESCRIPTOR (ntddk.h)
description: The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source.
old-location: whea\whea_error_source_descriptor.htm
tech.root: whea
ms.assetid: 59ee6d51-c60a-4a71-b831-1b9437a69d34
ms.date: 02/20/2018
ms.keywords: "*PWHEA_ERROR_SOURCE_DESCRIPTOR, PWHEA_ERROR_SOURCE_DESCRIPTOR, PWHEA_ERROR_SOURCE_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_ERROR_SOURCE_DESCRIPTOR, WHEA_ERROR_SOURCE_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_ERROR_SOURCE_DESCRIPTOR, ntddk/PWHEA_ERROR_SOURCE_DESCRIPTOR, ntddk/WHEA_ERROR_SOURCE_DESCRIPTOR, whea.whea_error_source_descriptor, whearef_eb6a1167-cf15-4a53-b885-c3d5c4353510.xml"
ms.topic: struct
f1_keywords:
 - "ntddk/WHEA_ERROR_SOURCE_DESCRIPTOR"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
- ntddk.h
api_name:
- WHEA_ERROR_SOURCE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_SOURCE_DESCRIPTOR, WHEA_ERROR_SOURCE_DESCRIPTOR"
ms.custom: 19H1
---

# _WHEA_ERROR_SOURCE_DESCRIPTOR structure


## -description


The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source.


## -struct-fields




### -field Length

The size, in bytes, of the WHEA_ERROR_SOURCE_DESCRIPTOR structure.


### -field Version

The version number of the WHEA_ERROR_SOURCE_DESCRIPTOR structure. This member contains the value WHEA_ERROR_SOURCE_DESCRIPTOR_VERSION_10.


### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a>-typed value that specifies the type of the error source.


### -field State

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_whea_error_source_state">WHEA_ERROR_SOURCE_STATE</a>-typed value that specifies the state of the error source.


### -field MaxRawDataLength

The maximum number of bytes of raw data included in a hardware error packet that is reported by this error source. This number must be large enough to include any additional platform-specific error information that is added to the hardware error packet by the PSHED or by a PSHED plug-in.


### -field NumRecordsToPreallocate

The number of error records that should be pre-allocated for hardware errors that are reported by this error source.


### -field MaxSectionsPerRecord

The maximum number of error record sections that are required in an error record to describe a hardware error that is reported by this error source. This number must be large enough to include any additional error record sections that are added to the error record by the PSHED or by a PSHED plug-in during the processing of the error.


### -field ErrorSourceId

The identifier of the error source. This identifier is unique only on the system where the error source exists.


### -field PlatformErrorSourceId

The identifier of the error source as enumerated by the hardware platform. This identifier is unique only on the system where the error source exists.


### -field Flags

A bitwise OR'ed combination of flags that describes the error source. Possible flags are:





#### WHEA_ERROR_SOURCE_FLAG_DEFAULTSOURCE

This flag indicates that the error source is a default error source for the type of hardware platform on which it exists.



#### WHEA_ERROR_SOURCE_FLAG_FIRMWAREFIRST

This flag indicates that the errors that are reported by this error source are handled by the firmware before control of the hardware error processing is passed to the operating system.



#### WHEA_ERROR_SOURCE_FLAG_GLOBAL

This flag indicates that the settings specified for the error source are to be applied to all of the error sources in the system that are of the same type as that specified in the <b>Type</b> member.


### -field Info

A union of descriptor structures that are specific to each different type of error source.


### -field Info.XpfMceDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_mce_descriptor">WHEA_XPF_MCE_DESCRIPTOR</a> structure that describes an x86 or x64 processor machine check exception (MCE) error source.


### -field Info.XpfCmcDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_cmc_descriptor">WHEA_XPF_CMC_DESCRIPTOR</a> structure that describes an x86 or x64 processor corrected machine check (CMC) error source.


### -field Info.XpfNmiDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_nmi_descriptor">WHEA_XPF_NMI_DESCRIPTOR</a> structure that describes an x86 or x64 processor nonmaskable interrupt (NMI) error source.


### -field Info.IpfMcaDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_mca_descriptor">WHEA_IPF_MCA_DESCRIPTOR</a> structure that describes an Itanium processor machine check abort (MCA) error source.


### -field Info.IpfCmcDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_cmc_descriptor">WHEA_IPF_CMC_DESCRIPTOR</a> structure that describes an Itanium processor corrected machine check (CMC) error source.


### -field Info.IpfCpeDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_cpe_descriptor">WHEA_IPF_CPE_DESCRIPTOR</a> structure that describes an Itanium processor corrected platform error (CPE) error source.


### -field Info.AerRootportDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_rootport_descriptor">WHEA_AER_ROOTPORT_DESCRIPTOR</a> structure that describes a PCI Express (PCIe) root port error source.


### -field Info.AerEndpointDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_endpoint_descriptor">WHEA_AER_ENDPOINT_DESCRIPTOR</a> structure that describes a PCIe endpoint error source. 


### -field Info.AerBridgeDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_bridge_descriptor">WHEA_AER_BRIDGE_DESCRIPTOR</a> structure that describes a PCIe bridge error source.


### -field Info.GenErrDescriptor

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_generic_error_descriptor">WHEA_GENERIC_ERROR_DESCRIPTOR</a> structure that describes a generic error source.


### -field Info.GenErrDescriptorV2

### -field Info.DeviceDriverDescriptor

A [WHEA_DEVICE_DRIVER_DESCRIPTOR](ns-ntddk-whea_device_driver_descriptor.md) structure.


## -remarks



The WHEA_ERROR_SOURCE_DESCRIPTOR structure describes an error source. The WHEA_ERROR_SOURCE_DESCRIPTOR structure is also used to configure an error source.

A user-mode WHEA management application can control the error sources in the system by calling the methods in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods</a> WMI provider class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_disable_error_source">DisableErrorSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_enable_error_source">EnableErrorSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_all_error_sources">GetAllErrorSources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_get_error_source_info">GetErrorSourceInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nc-ntddk-pshed_pi_set_error_source_info">SetErrorSourceInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods::DisableErrorSourceRtn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods::EnableErrorSourceRtn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods::GetAllErrorSourcesRtn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods::GetErrorSourceInfoRtn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_whea/">WHEAErrorSourceMethods::SetErrorSourceInfoRtn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_bridge_descriptor">WHEA_AER_BRIDGE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_endpoint_descriptor">WHEA_AER_ENDPOINT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_aer_rootport_descriptor">WHEA_AER_ROOTPORT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_whea_error_source_state">WHEA_ERROR_SOURCE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ne-ntddk-_whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_generic_error_descriptor">WHEA_GENERIC_ERROR_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_cmc_descriptor">WHEA_IPF_CMC_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_cpe_descriptor">WHEA_IPF_CPE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_ipf_mca_descriptor">WHEA_IPF_MCA_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_cmc_descriptor">WHEA_XPF_CMC_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_mce_descriptor">WHEA_XPF_MCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/ns-ntddk-_whea_xpf_nmi_descriptor">WHEA_XPF_NMI_DESCRIPTOR</a>
 

 

