---
UID: NS:ntddndis._NDIS_SWITCH_PORT_PROPERTY_PROFILE
title: "_NDIS_SWITCH_PORT_PROPERTY_PROFILE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_PROPERTY_PROFILE structure specifies a policy property for a Hyper-V extensible switch port that the extensible switch extension saves in its own policy store instead of in the Hyper-V policy store.
old-location: netvista\ndis_switch_port_property_profile.htm
old-project: netvista
ms.assetid: DFB7239F-4A6B-4C98-884E-FAC1A0DE2024
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNDIS_SWITCH_PORT_PROPERTY_PROFILE, NDIS_SWITCH_PORT_PROPERTY_PROFILE, NDIS_SWITCH_PORT_PROPERTY_PROFILE structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_PROPERTY_PROFILE, PNDIS_SWITCH_PORT_PROPERTY_PROFILE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_PROPERTY_PROFILE, netvista.ndis_switch_port_property_profile, ntddndis/NDIS_SWITCH_PORT_PROPERTY_PROFILE, ntddndis/PNDIS_SWITCH_PORT_PROPERTY_PROFILE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	Ntddndis.h
api_name:
-	NDIS_SWITCH_PORT_PROPERTY_PROFILE
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_PROPERTY_PROFILE, *PNDIS_SWITCH_PORT_PROPERTY_PROFILE
---

# _NDIS_SWITCH_PORT_PROPERTY_PROFILE structure


## -description


The <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure specifies a policy property for a Hyper-V extensible switch port that the extensible switch extension saves in its own policy store instead of in the Hyper-V policy store. In this case, policy definitions are identified by property profiles within the driver's policy store.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:





#### NDIS_SWITCH_PORT_PROPERTY_PROFILE_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_PROFILE_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field ProfileName

An NDIS_SWITCH_PORT_PROPERTY_PROFILE_NAME value that specifies the user-friendly name of the profile property.


### -field ProfileId

A GUID value that uniquely identifies the profile property.


### -field VendorName

An NDIS_VENDOR_NAME value that specifies the user-friendly name of the vendor that defined the port profile.


### -field VendorId

A GUID value that identifies the vendor that defined the port profile.


### -field ProfileData

 


### -field NetCfgInstanceId

A GUID value that specifies the <b>NetCfgInstanceId</b> registry value of the underlying network adapter connection for which the property is applied.



The <b>NetCfgInstanceId</b> value is specified for the network adapter connection through an object identifier (OID) set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598263">OID_SWITCH_NIC_CREATE</a>.


### -field PciLocation

A structure that specifies the PCI location of the underlying physical network adapter that is specified by the <b>NetCfgInstanceId</b> member.

For more information, see the Remarks section.


### -field PciLocation.PciSegmentNumber

A value that specifies the group of PCI buses on which the physical network adapter is attached.



### -field PciLocation.PciBusNumber

A value that specifies the current PCI bus number on which the physical network adapter is attached.



### -field PciLocation.PciDeviceNumber

A value that specifies the device number for the physical network adapter on the PCI bus.


<div class="alert"><b>Note</b>  The PCI device number is also known as the <i>PCI slot number</i>.</div>
<div> </div>

### -field PciLocation.PciFunctionNumber

A value that specifies the function number of a logical device on the physical network adapter.


### -field CdnLabelId

A UINT32 value that specifies a unique identifier for the data that is contained in the <b>CdnLabel</b> member.


### -field CdnLabel

An  NDIS_SWITCH_PORT_PROPERTY_PROFILE_CDN_LABEL value that specifies the PCI Express (PCIe) CDN label for the location of the physical network adapter. A CDN label provides consistent device locations across similar hardware locations.


#### - BindingType

A UINT32 value that contains a proprietary value that is defined by the independent software vendor (ISV).


## -remarks



The <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure is used by the extension to reference a policy property within a private policy store instead of the Hyper-V policy store. This allows the independent software vendor (ISV) to populate and manage this private policy store through private channels and interfaces.  Vendors can distinguish their profiles from other vendors' profiles using the <i>VendorName</i> and <i>VendorId</i> fields. 

<div class="alert"><b>Note</b>  Port policy properties specified by an <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure are transparent to the extensible switch interface. </div>
<div> </div>
The <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure is used in the following OID set requests: 

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>


</li>
</ul>
The <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE</b> structure follows the <a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a> structure in the buffer that is associated with these OID set requests. The <b>InformationBuffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure contains a pointer to this buffer.

<div class="alert"><b>Note</b>  The <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE_NAME</b> and <b>NDIS_SWITCH_PORT_PROPERTY_PROFILE_CDN_LABEL</b> data types are type-defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a> structure. A string that is defined by this structure does not have to be null-terminated. However, the length of the string must be set in the <b>Length</b> member of this structure. If the string is null-terminated, the <b>Length</b> member must not include the terminating null character. 
</div>
<div> </div>
The <b>PciLocation</b> and <b>CdnLabel</b> members are only relevant if the property profile specifies a policy for an underlying physical network adapter that is attached to the extensible switch external network adapter. For example, if the external network adapter is bound to an extensible switch team of adapters, these members could specify policies for a single adapter from that team. For more information about the extensible switch team, see <a href="https://msdn.microsoft.com/83F71AF7-A807-4F81-A0B3-1777135AAE39">Types of Physical Network Adapter Configurations</a>.




## -see-also




<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451419">IF_COUNTED_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598238">NDIS_SWITCH_PORT_PROPERTY_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598263">OID_SWITCH_NIC_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598275">OID_SWITCH_PORT_PROPERTY_ADD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598278">OID_SWITCH_PORT_PROPERTY_UPDATE</a>
 

 

