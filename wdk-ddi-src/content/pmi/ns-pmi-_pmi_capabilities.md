---
UID: NS:pmi._PMI_CAPABILITIES
title: "_PMI_CAPABILITIES"
author: windows-driver-content
description: The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.
old-location: powermeter\pmi_capabilities.htm
old-project: powermeter
ms.assetid: 7e564512-ff57-4bce-93c1-76e6034ec061
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PPMI_CAPABILITIES, PowerMeterRef_14d27676-6523-4aca-8ce7-c6c3e8794171.xml, pmi/PMI_CAPABILITIES, PPMI_CAPABILITIES, PMI_CAPABILITIES structure [Power Metering and Budgeting Devices], pmi/PPMI_CAPABILITIES, PMI_CAPABILITIES, _PMI_CAPABILITIES, powermeter.pmi_capabilities, PPMI_CAPABILITIES structure pointer [Power Metering and Budgeting Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pmi.h
apiname:
-	PMI_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PPMI_CAPABILITIES, PMI_CAPABILITIES"
---

# _PMI_CAPABILITIES structure


## -description


The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.


## -syntax


````
typedef struct _PMI_CAPABILITIES {
  ULONG                 Version;
  ULONG                 Size;
  PMI_CAPABILITIES_TYPE CapabilityType;
  union {
    PMI_REPORTED_CAPABILITIES        ReportedCapabilities;
    PMI_METERED_HARDWARE_INFORMATION MeteredHardwareInformation;
  } Capabilities;
} PMI_CAPABILITIES, *PPMI_CAPABILITIES;
````


## -struct-fields




#### - Capabilities

A union of the supported Power Meter Interface (PMI) capability structures. Based on the value of the <b>CapabilityType</b> member, one of the following <b>Capabilities</b> submembers is used to reference the following PMI capability structures:


#### ReportedCapabilities

A <a href="..\pmi\ns-pmi-_pmi_metered_hardware_information.md">PMI_METERED_HARDWARE_INFORMATION</a> structure that specifies one or more hardware devices that are monitored by the power meter. 

The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiMeteredHardware</b>.


#### MeteredHardwareInformation

A <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure that specifies the PMI capabilities of the power meter, such as the following:
<ul>
<li>Asset information 
</li>
<li>Measurement capabilities 
</li>
<li>Power and budget capabilities 
</li>
</ul>The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiReportedCapabilities</b>.


### -field Capabilities.ReportedCapabilities

A <a href="..\pmi\ns-pmi-_pmi_metered_hardware_information.md">PMI_METERED_HARDWARE_INFORMATION</a> structure that specifies one or more hardware devices that are monitored by the power meter. 

The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiMeteredHardware</b>.


### -field Capabilities.MeteredHardwareInformation

A <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure that specifies the PMI capabilities of the power meter, such as the following:
<ul>
<li>Asset information 
</li>
<li>Measurement capabilities 
</li>
<li>Power and budget capabilities 
</li>
</ul>The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiReportedCapabilities</b>.


#### - Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


#### - Size

A value, in units of bytes, that specifies the size of the structure.


#### - CapabilityType

A <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumeration value that specifies the data type of the <b>Capabilities</b> member.


## -remarks


The PMI_CAPABILITIES structure is used to query many PMI capabilities that are supported by a power meter. 

The PMI capability information is returned through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to a <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumerator value that specifies the type of PMI capability data to return.

If the IOCTL query request completes successfully, the request returns a PMI_CAPABILITIES structure. The <b>Capabilities</b> member of this structure contains data formatted as the requested PMI capabilities structure.

For example, if an IOCTL query request of <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> is made with the input data set to <b>PmiReportedCapabilities</b> and the request completes successfully, the request returns a PMI_CAPABILITIES structure with its members set to the following values:
<ul>
<li>
The <b>CapabilitiesType</b> member is set to <b>PmiReportedCapabilities</b>.

</li>
<li>
The <b>Capabilities</b> member contains data that is formatted as a <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure.

</li>
</ul>


## -see-also

<a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>

<a href="..\pmi\ns-pmi-_pmi_metered_hardware_information.md">PMI_METERED_HARDWARE_INFORMATION</a>

<a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_CAPABILITIES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

