---
UID: NE:pmi.__unnamed_enum_0
title: PMI_CAPABILITIES_TYPE (pmi.h)
description: The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the Capability member of the PMI_CAPABILITIES structure.
old-location: powermeter\pmi_capabilities_type.htm
tech.root: powermeter
ms.assetid: 6857f85b-c79a-4e80-a63f-1414aff61d1f
ms.date: 05/08/2018
ms.keywords: PMI_CAPABILITIES_TYPE, PMI_CAPABILITIES_TYPE enumeration [Power Metering and Budgeting Devices], PmiCapabilitiesMax, PmiMeteredHardware, PmiReportedCapabilities, PowerMeterRef_4b81a5dd-357b-4a02-acc6-3a0538cbeffb.xml, pmi/PMI_CAPABILITIES_TYPE, pmi/PmiCapabilitiesMax, pmi/PmiMeteredHardware, pmi/PmiReportedCapabilities, powermeter.pmi_capabilities_type
ms.topic: enum
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
- pmi.h
api_name:
- PMI_CAPABILITIES_TYPE
product:
- Windows
targetos: Windows
req.typenames: PMI_CAPABILITIES_TYPE
---

# PMI_CAPABILITIES_TYPE enumeration


## -description


The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the <b>Capability</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure. This enumeration is also used to specify the type of <b>PMI_CAPABILITIES</b> structure to return through an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) request.


## -enum-fields




### -field PmiReportedCapabilities

The PMI capabilities data, formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure, specifies the power capabilities of the power meter.


### -field PmiMeteredHardware

The PMI capabilities data, formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a> structure, specifies the hardware devices that the power meter provides measurement data to.


### -field PmiCapabilitiesMax

The maximum number of PMI capability structures.


## -remarks



The <b>CapabilityType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure contains information about the type of PMI capability data that is referenced by the <b>Capabilities</b> member of that structure. This structure is returned through a successful completion of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a> IOCTL request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
 

 

