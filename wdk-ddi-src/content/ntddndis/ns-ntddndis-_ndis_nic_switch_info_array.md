---
UID: NS:ntddndis._NDIS_NIC_SWITCH_INFO_ARRAY
title: "_NDIS_NIC_SWITCH_INFO_ARRAY"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a network adapter switch that has been created on the network adapter.
old-location: netvista\ndis_nic_switch_info_array.htm
old-project: netvista
ms.assetid: bff2b133-bbef-4f2a-a7b1-34d7cf364205
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddndis/NDIS_NIC_SWITCH_INFO_ARRAY, NDIS_NIC_SWITCH_INFO_ARRAY, PNDIS_NIC_SWITCH_INFO_ARRAY, PNDIS_NIC_SWITCH_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_NIC_SWITCH_INFO_ARRAY, _NDIS_NIC_SWITCH_INFO_ARRAY, *PNDIS_NIC_SWITCH_INFO_ARRAY, NDIS_NIC_SWITCH_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], netvista.ndis_nic_switch_info_array
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
-	NDIS_NIC_SWITCH_INFO_ARRAY
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_INFO_ARRAY, *PNDIS_NIC_SWITCH_INFO_ARRAY
---

# _NDIS_NIC_SWITCH_INFO_ARRAY structure


## -description


The <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes  of a network adapter switch that has been created on the network adapter.


## -syntax


````
typedef struct _NDIS_NIC_SWITCH_INFO_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              FirstElementOffset;
  ULONG              NumElements;
  ULONG              ElementSize;
} NDIS_NIC_SWITCH_INFO_ARRAY, *PNDIS_NIC_SWITCH_INFO_ARRAY;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_INFO_ARRAY_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_INFO_ARRAY_REVISION_1.


### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info.md">NDIS_NIC_SWITCH_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure. 


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each element that follows the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure.


## -remarks



NDIS returns an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure in the following ways:

<ul>
<li>
When NDIS handles an OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451819">OID_NIC_SWITCH_ENUM_SWITCHES</a>, it returns a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure in the <b>InformationBuffer</b> member of the <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>.

</li>
<li>When NDIS calls the <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
function, NDIS passes a pointer to an <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure in the <i>BindParameters</i> parameter. NDIS sets the  <b>NicSwitchArray</b> member of the <b>NDIS_BIND_PARAMETERS</b> structure to a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure. </li>
<li>When NDIS calls the <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
function, NDIS passes a pointer to an <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a> structure in the <i>AttachParameters</i> parameter. NDIS sets the  <b>NicSwitchArray</b> member of the <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure to a pointer to an <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure.</li>
</ul>
Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_INFO_ARRAY</b> structure is an 
    
    <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info.md">NDIS_NIC_SWITCH_INFO</a> structure.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, only the <b>NDIS_NIC_SWITCH_INFO</b> that describes the information about the default network adapter switch is returned through an OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451819">OID_NIC_SWITCH_ENUM_SWITCHES</a>.</div>
<div> </div>



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info.md">NDIS_NIC_SWITCH_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>



<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451819">OID_NIC_SWITCH_ENUM_SWITCHES</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_INFO_ARRAY structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

