---
UID: NS:ndis._NDIS_SWITCH_OPTIONAL_HANDLERS
title: "_NDIS_SWITCH_OPTIONAL_HANDLERS"
author: windows-driver-content
description: The NDIS_SWITCH_OPTIONAL_HANDLERS structure specifies the pointers to the Hyper-V extensible switch handler functions. These functions can be called by an extensible switch extension.
old-location: netvista\ndis_switch_optional_handlers.htm
old-project: netvista
ms.assetid: aa8367c7-8366-4601-8c2a-4d96df5cfcd8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_SWITCH_OPTIONAL_HANDLERS, NDIS_SWITCH_OPTIONAL_HANDLERS, NDIS_SWITCH_OPTIONAL_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_OPTIONAL_HANDLERS, PNDIS_SWITCH_OPTIONAL_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_OPTIONAL_HANDLERS, ndis/NDIS_SWITCH_OPTIONAL_HANDLERS, ndis/PNDIS_SWITCH_OPTIONAL_HANDLERS, netvista.ndis_switch_optional_handlers"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ndis.h
api_name:
-	NDIS_SWITCH_OPTIONAL_HANDLERS
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_OPTIONAL_HANDLERS, *PNDIS_SWITCH_OPTIONAL_HANDLERS
---

# _NDIS_SWITCH_OPTIONAL_HANDLERS structure


## -description


The <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure specifies the pointers to the Hyper-V extensible switch handler functions. These functions can be called by an extensible switch extension.


## -syntax


````
typedef struct _NDIS_SWITCH_OPTIONAL_HANDLERS {
  NDIS_OBJECT_HEADER                                              Header;
  NDIS_SWITCH_ALLOCATE_NET_BUFFER_LIST_FORWARDING_CONTEXT_HANDLER AllocateNetBufferListForwardingContext;
  NDIS_SWITCH_FREE_NET_BUFFER_LIST_FORWARDING_CONTEXT_HANDLER     FreeNetBufferListForwardingContext;
  NDIS_SWITCH_SET_NET_BUFFER_LIST_SOURCE_HANDLER                  SetNetBufferListSource;
  NDIS_SWITCH_ADD_NET_BUFFER_LIST_DESTINATION_HANDLER             AddNetBufferListDestination;
  NDIS_SWITCH_GROW_NET_BUFFER_LIST_DESTINATIONS_HANDLER           GrowNetBufferListDestinations;
  NDIS_SWITCH_GET_NET_BUFFER_LIST_DESTINATIONS_HANDLER            GetNetBufferListDestinations;
  NDIS_SWITCH_UPDATE_NET_BUFFER_LIST_DESTINATIONS_HANDLER         UpdateNetBufferListDestinations;
  NDIS_SWITCH_COPY_NET_BUFFER_LIST_INFO_HANDLER                   CopyNetBufferListInfo;
  NDIS_SWITCH_REFERENCE_SWITCH_NIC_HANDLER                        ReferenceSwitchNic;
  NDIS_SWITCH_DEREFERENCE_SWITCH_NIC_HANDLER                      DereferenceSwitchNic;
  NDIS_SWITCH_REFERENCE_SWITCH_PORT_HANDLER                       ReferenceSwitchPort;
  NDIS_SWITCH_DEREFERENCE_SWITCH_PORT_HANDLER                     DereferenceSwitchPort;
  NDIS_SWITCH_REPORT_FILTERED_NET_BUFFER_LISTS_HANDLER            ReportFilteredNetBufferLists;
} NDIS_SWITCH_OPTIONAL_HANDLERS, *PNDIS_SWITCH_OPTIONAL_HANDLERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_OPTIONAL_HANDLERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_NIC_ARRAY_REVISION_1.


### -field AllocateNetBufferListForwardingContext

A pointer to the <a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a> function.


### -field FreeNetBufferListForwardingContext

A pointer to the <a href="https://msdn.microsoft.com/08AE3160-276F-4D1F-9D02-AD5AF38CDED2">FreeNetBufferListForwardingContext</a> function.


### -field SetNetBufferListSource

A pointer to the <a href="..\ndis\nc-ndis-ndis_switch_set_net_buffer_list_source.md">SetNetBufferListSource</a> function.


### -field AddNetBufferListDestination

A pointer to the <a href="https://msdn.microsoft.com/6B8CD868-D2F4-4892-BF6D-DFD7A3984320">AddNetBufferListDestination</a> function.


### -field GrowNetBufferListDestinations

A pointer to the <a href="..\ndis\nc-ndis-ndis_switch_grow_net_buffer_list_destinations.md">GrowNetBufferListDestinations</a> function.


### -field GetNetBufferListDestinations

A pointer to the <a href="https://msdn.microsoft.com/55B5C0B4-5359-410B-9110-79EDDBA3010C">GetNetBufferListDestinations</a> function.


### -field UpdateNetBufferListDestinations

A pointer to the <a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a> function.


### -field CopyNetBufferListInfo

A pointer to the <a href="https://msdn.microsoft.com/5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A">CopyNetBufferListInfo</a> function.


### -field ReferenceSwitchNic

A pointer to the <a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a> function.


### -field DereferenceSwitchNic

A pointer to the <a href="https://msdn.microsoft.com/58C72F81-07B9-45FE-A8BA-0405DBE4CA20">DereferenceSwitchNic</a> function.


### -field ReferenceSwitchPort

A pointer to the <a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a> function.


### -field DereferenceSwitchPort

A pointer to the <a href="https://msdn.microsoft.com/976D3A69-C539-4C8E-9664-F85717E5F712">DereferenceSwitchPort</a> function.


### -field ReportFilteredNetBufferLists

A pointer to the <a href="..\ndis\nc-ndis-ndis_switch_report_filtered_net_buffer_lists.md">ReportFilteredNetBufferLists</a> function.


### -field SetNetBufferListSwitchContext

 


### -field GetNetBufferListSwitchContext

 


### -field SwitchPDReserved

 




## -remarks



The extensible switch handler functions provide support for filtering and forwarding actions that are performed by an extensible switch extension. These actions include the following:


<ul>
<li>
Allocate or free  the forwarding context. This data is stored in the out-of-band (OOB) data of a packet's  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. For more information about the forwarding context, see <a href="https://msdn.microsoft.com/B2BF07B5-FA44-4994-9605-EFF4A0B9179F">Hyper-V Extensible Switch Forwarding Context</a>.

</li>
<li>
Get or set the destination ports that are contained in a packet's forwarding context.

</li>
<li>
Add destination ports to a packet's forwarding context.

</li>
</ul>


When the extensible switch extension calls <a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>, the <i>NdisSwitchHandlers</i> parameter contains a pointer to an  <b>NDIS_SWITCH_OPTIONAL_HANDLERS</b> structure. An extensible switch extension typically calls <b>NdisFGetOptionalSwitchHandlers</b> from its <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.




## -see-also

<a href="https://msdn.microsoft.com/5FD2E931-AC9F-4157-9C45-F93261FC834D">ReferenceSwitchPort</a>



<a href="https://msdn.microsoft.com/C8A80DB2-4273-4FBA-82D4-4E8146812B16">AllocateNetBufferListForwardingContext</a>



<a href="..\ndis\nc-ndis-ndis_switch_set_net_buffer_list_source.md">SetNetBufferListSource</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-ndis_switch_grow_net_buffer_list_destinations.md">GrowNetBufferListDestinations</a>



<a href="https://msdn.microsoft.com/976D3A69-C539-4C8E-9664-F85717E5F712">DereferenceSwitchPort</a>



<a href="https://msdn.microsoft.com/6B8CD868-D2F4-4892-BF6D-DFD7A3984320">AddNetBufferListDestination</a>



<a href="https://msdn.microsoft.com/58C72F81-07B9-45FE-A8BA-0405DBE4CA20">DereferenceSwitchNic</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-ndis_switch_report_filtered_net_buffer_lists.md">ReportFilteredNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndisfgetoptionalswitchhandlers.md">NdisFGetOptionalSwitchHandlers</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/9A740524-0FC1-4585-8059-F678D4777F66">UpdateNetBufferListDestinations</a>



<a href="https://msdn.microsoft.com/8F4C76FA-A386-4A3D-8C9F-3CFF69382702">ReferenceSwitchNic</a>



<a href="https://msdn.microsoft.com/08AE3160-276F-4D1F-9D02-AD5AF38CDED2">FreeNetBufferListForwardingContext</a>



<a href="https://msdn.microsoft.com/5CC345FA-C3EF-4122-8E9C-6EA27B20DD5A">CopyNetBufferListInfo</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_OPTIONAL_HANDLERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

