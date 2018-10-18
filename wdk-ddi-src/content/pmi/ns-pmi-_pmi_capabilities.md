---
UID: NS:pmi._PMI_CAPABILITIES
title: "_PMI_CAPABILITIES"
author: windows-driver-content
description: The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.
old-location: powermeter\pmi_capabilities.htm
tech.root: powermeter
ms.assetid: 7e564512-ff57-4bce-93c1-76e6034ec061
ms.date: 5/8/2018
ms.keywords: "*PPMI_CAPABILITIES, PMI_CAPABILITIES, PMI_CAPABILITIES structure [Power Metering and Budgeting Devices], PPMI_CAPABILITIES, PPMI_CAPABILITIES structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_14d27676-6523-4aca-8ce7-c6c3e8794171.xml, _PMI_CAPABILITIES, pmi/PMI_CAPABILITIES, pmi/PPMI_CAPABILITIES, powermeter.pmi_capabilities"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pmi.h
api_name:
-	PMI_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: PMI_CAPABILITIES, *PPMI_CAPABILITIES
---

# _PMI_CAPABILITIES structure


## -description


The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.


## -struct-fields




### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


### -field Size

A value, in units of bytes, that specifies the size of the structure.


### -field CapabilityType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a> enumeration value that specifies the data type of the <b>Capabilities</b> member.


### -field Capabilities

A union of the supported Power Meter Interface (PMI) capability structures. Based on the value of the <b>CapabilityType</b> member, one of the following <b>Capabilities</b> submembers is used to reference the following PMI capability structures:


### -field Capabilities.ReportedCapabilities

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543900">PMI_METERED_HARDWARE_INFORMATION</a> structure that specifies one or more hardware devices that are monitored by the power meter. 

The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiMeteredHardware</b>.


### -field Capabilities.MeteredHardwareInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a> structure that specifies the PMI capabilities of the power meter, such as the following:

<ul>
<li>Asset information 
</li>
<li>Measurement capabilities 
</li>
<li>Power and budget capabilities 
</li>
</ul>
The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiReportedCapabilities</b>.


## -remarks



The PMI_CAPABILITIES structure is used to query many PMI capabilities that are supported by a power meter. 

The PMI capability information is returned through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a> enumerator value that specifies the type of PMI capability data to return.

If the IOCTL query request completes successfully, the request returns a PMI_CAPABILITIES structure. The <b>Capabilities</b> member of this structure contains data formatted as the requested PMI capabilities structure.

For example, if an IOCTL query request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> is made with the input data set to <b>PmiReportedCapabilities</b> and the request completes successfully, the request returns a PMI_CAPABILITIES structure with its members set to the following values:

<ul>
<li>
The <b>CapabilitiesType</b> member is set to <b>PmiReportedCapabilities</b>.

</li>
<li>
The <b>Capabilities</b> member contains data that is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a> structure.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543900">PMI_METERED_HARDWARE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a>
 

 

