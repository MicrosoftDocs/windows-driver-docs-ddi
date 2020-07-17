---
UID: NS:ehstorioctl._SILO_DRIVER_CAPABILITIES
title: _SILO_DRIVER_CAPABILITIES (ehstorioctl.h)
description: This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. SILO_DRIVER_CAPABILITIES is included in the system buffer of an IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES request.
old-location: storage\silo_driver_capabilities.htm
tech.root: storage
ms.assetid: E2CD35A6-0FF2-4ABA-850E-12683C5F0D8D
ms.date: 03/29/2018
keywords: ["_SILO_DRIVER_CAPABILITIES structure"]
ms.keywords: "*PSILO_DRIVER_CAPABILITIES, CAP_BANDING_SUPPORT, CAP_ON_DEMAND_AUTHENTICATION, PSILO_DRIVER_CAPABILITIES, PSILO_DRIVER_CAPABILITIES structure pointer [Storage Devices], SILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES structure [Storage Devices], _SILO_DRIVER_CAPABILITIES, ehstorioctl/PSILO_DRIVER_CAPABILITIES, ehstorioctl/SILO_DRIVER_CAPABILITIES, storage.silo_driver_capabilities"
f1_keywords:
 - "ehstorioctl/SILO_DRIVER_CAPABILITIES"
 - "SILO_DRIVER_CAPABILITIES"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
- EhStorIoctl.h
api_name:
- SILO_DRIVER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# _SILO_DRIVER_CAPABILITIES structure


## -description


This structure is used to specify the capabilities and support for IOCTL redirection of a storage silo driver. <b>SILO_DRIVER_CAPABILITIES</b> is included in the system buffer of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request.


## -struct-fields




### -field StructSize

The size of this structure. This is set to <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).


### -field Capabilities

Capability flags for the silo driver. This is a bitwise OR combination of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="CAP_ON_DEMAND_AUTHENTICATION"></a><a id="cap_on_demand_authentication"></a><dl>
<dt><b>CAP_ON_DEMAND_AUTHENTICATION</b></dt>
</dl>
</td>
<td width="60%">
The silo driver supports on-demand authentication and unauthentication.

</td>
</tr>
<tr>
<td width="40%"><a id="CAP_BANDING_SUPPORT"></a><a id="cap_banding_support"></a><dl>
<dt><b>CAP_BANDING_SUPPORT</b></dt>
</dl>
</td>
<td width="60%">
The silo driver supports banding of LBA ranges.

</td>
</tr>
</table>
 


### -field MaxLbaFilterCount

Maximum number of LBA filter entries the silo driver can provide in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a> request.


### -field RedirectedIoctlListCount

The number of redirected IOCTLs in the list following this structure.


### -field RedirectedIoctlListOffset

The offset of the redirected IOCTL list from the beginning of this structure. This will typically be <b>sizeof</b>(SILO_DRIVER_CAPABILITIES).


## -remarks



To support receiving <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_perform_authz">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a> from the enhanced storage class driver, a silo driver must set <b>CAP_ON_DEMAND_AUTHENTICATION</b> in <b>Capabilities</b>. Also, to support sending <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>, a silo driver must set <b>CAP_BANDING_SUPPORT</b> in <b>Capabilities</b>.

To receive band management requests from the enhanced storage class driver, a silo driver must register a list of IOCTL codes it wants to receive. The redirected IOCTL list is an array of <b>ULONG</b> IOCTL codes with a length of <b>RedirectedIoctlListCount</b>. This list is included with the <b>SILO_DRIVER_CAPABILITIES</b> structure in the system buffer. The list is located in the system buffer following  <b>SILO_DRIVER_CAPABILITIES</b> at the offset indicated by <b>RedirectedIoctlListOffset</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_perform_authz">IOCTL_EHSTOR_DRIVER_PERFORM_AUTHZ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ehstorioctl/ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table">IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE</a>
 

 

