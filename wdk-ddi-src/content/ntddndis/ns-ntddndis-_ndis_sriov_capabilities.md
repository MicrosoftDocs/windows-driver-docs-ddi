---
UID: NS:ntddndis._NDIS_SRIOV_CAPABILITIES
title: "_NDIS_SRIOV_CAPABILITIES"
author: windows-driver-content
description: The NDIS_SRIOV_CAPABILITIES structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.
old-location: netvista\ndis_sriov_capabilities.htm
old-project: netvista
ms.assetid: 57cf980c-4477-4c12-8d82-7a8df8b2922f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_SRIOV_CAPABILITIES structure pointer [Network Drivers Starting with Windows Vista], ntddndis/NDIS_SRIOV_CAPABILITIES, NDIS_SRIOV_CAPABILITIES, netvista.ndis_sriov_capabilities, PNDIS_SRIOV_CAPABILITIES, ntddndis/PNDIS_SRIOV_CAPABILITIES, _NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES, NDIS_SRIOV_CAPABILITIES structure [Network Drivers Starting with Windows Vista]
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SRIOV_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES
---

# _NDIS_SRIOV_CAPABILITIES structure


## -description


The <b>NDIS_SRIOV_CAPABILITIES</b> structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.


## -syntax


````
typedef struct _NDIS_SRIOV_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              SriovCapabilities;
} NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_CAPABILITIES</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_CAPABILITIES _REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_CAPABILITIES _REVISION_1.


### -field Flags

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS


### -field SriovCapabilities

A ULONG value that contains a bitwise OR of the following flags:





#### NDIS_SRIOV_CAPS_SRIOV_SUPPORTED

Specifies that the network adapter supports SR-IOV functionality. 

<div class="alert"><b>Note</b>  This flag must only be set by the miniport driver for the PCI Express (PCIe) Physical Function (PF) of the network adapter. This driver runs in the management operating system. This operating system runs in the Hyper-V parent partition.</div>
<div> </div>


#### NDIS_SRIOV_CAPS_PF_MINIPORT

Specifies that this is a PF  miniport driver. 



#### NDIS_SRIOV_CAPS_VF_MINIPORT

Specifies that this is a PCIe  Virtual Function (VF) miniport driver. 


## -remarks



 The miniport driver uses the <b>NDIS_SRIOV_CAPABILITIES</b> structure to report its SR-IOV capabilities in the following ways:

<ul>
<li>
The  miniport driver calls the <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a> function from its <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function and sets the <i>MiniportAttributes</i> parameter to a pointer to an  <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure. The driver advertises SR-IOV support by formatting the 
<b>HardwareSriovCapabilities</b> and <b>CurrentSriovCapabilities</b> members as <b>NDIS_SRIOV_CAPABILITIES</b> structures.

</li>
<li>When the driver successfully handles an OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451862">OID_SRIOV_HARDWARE_CAPABILITIES</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/hh451859">OID_SRIOV_CURRENT_CAPABILITIES</a>, it returns an <b>NDIS_SRIOV_CAPABILITIES</b> structure.</li>
</ul>
NDIS passes the network adapter's SR-IOV capabilities to overlying drivers that bind to the network adapter in the following way:

<ul>
<li>
When NDIS calls an overlying filter driver's <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function, NDIS passes the network adapter's SR-IOV capabilities through the <i>AttachParameters</i> parameter.  This parameter contains a pointer to an <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.

</li>
<li>
When NDIS calls an overlying protocol driver's <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
 function, NDIS passes the network adapter's SR-IOV capabilities through the <i>BindParameters</i> parameter.  This parameter contains a pointer to an <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.

</li>
</ul>
For more information on how to report the SR-IOV capabilities of a network adapter, see <a href="https://msdn.microsoft.com/61895987-2469-471E-BB29-FF1CDD2869DC">Determining SR-IOV Capabilities</a>.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff559389">MiniportInitializeEx</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451859">OID_SRIOV_CURRENT_CAPABILITIES</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451862">OID_SRIOV_HARDWARE_CAPABILITIES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_hardware_assist_attributes.md">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_CAPABILITIES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

