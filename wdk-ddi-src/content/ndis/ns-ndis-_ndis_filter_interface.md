---
UID: NS:ndis._NDIS_FILTER_INTERFACE
title: _NDIS_FILTER_INTERFACE (ndis.h)
description: The NDIS_FILTER_INTERFACE structure defines the attributes for an NDIS filter.
old-location: netvista\ndis_filter_interface.htm
tech.root: netvista
ms.assetid: 0a765829-3558-48ea-b788-7cce6c4b64c6
ms.date: 05/02/2018
keywords: ["NDIS_FILTER_INTERFACE structure"]
ms.keywords: "*PNDIS_FILTER_INTERFACE, NDIS_FILTER_INTERFACE, NDIS_FILTER_INTERFACE structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_INTERFACE, PNDIS_FILTER_INTERFACE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_INTERFACE, filter_structures_ref_ec1f81f5-4aac-4e69-a8e1-96bc0c5f9958.xml, ndis/NDIS_FILTER_INTERFACE, ndis/PNDIS_FILTER_INTERFACE, netvista.ndis_filter_interface"
f1_keywords:
 - "ndis/NDIS_FILTER_INTERFACE"
 - "NDIS_FILTER_INTERFACE"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
- ndis.h
api_name:
- NDIS_FILTER_INTERFACE
targetos: Windows
req.typenames: NDIS_FILTER_INTERFACE, *PNDIS_FILTER_INTERFACE
---

# _NDIS_FILTER_INTERFACE structure


## -description


The NDIS_FILTER_INTERFACE structure defines the attributes for an NDIS filter.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     filter interface structure. 

NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

If the handle passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisenumeratefiltermodules">NdisEnumerateFilterModules</a> belongs to an NDIS 6.30 or later object, then NDIS sets <b>Revision</b> to NDIS_FILTER_INTERFACE_REVISION_2 and <b>Size</b> to NDIS_SIZEOF_FILTER_INTERFACE_REVISION_2.

If the handle passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisenumeratefiltermodules">NdisEnumerateFilterModules</a> belongs to an NDIS 6.20 or earlier object, then NDIS sets <b>Revision</b> to NDIS_FILTER_INTERFACE_REVISION_1 and <b>Size</b> to NDIS_SIZEOF_FILTER_INTERFACE_REVISION_1.


### -field Flags

A bit field that defines the type of NDIS driver that implements the filter. This member must be
     set to one of the following driver types:
     





#### NDIS_FILTER_INTERFACE_IM_FILTER

The filter is implemented in an NDIS 5.1 or earlier filter intermediate driver.



#### NDIS_FILTER_INTERFACE_LW_FILTER

The filter is implemented in an NDIS 6.0 or later filter driver.



#### NDIS_FILTER_INTERFACE_SEND_BYPASS

The filter is currently not attached to the send path.  This flag is only set if <b>Header.Revision</b> is greater than or equal to NDIS_FILTER_INTERFACE_REVISION_2.



#### NDIS_FILTER_INTERFACE_RECEIVE_BYPASS

The filter is currently not attached to the receive path.  This flag is only set if <b>Header.Revision</b> is greater than or equal to NDIS_FILTER_INTERFACE_REVISION_2.



### -field FilterType

The behavior type for the filter. This type must be one of the following values:
     





#### NdisFilterTypeMonitoring = 1

A monitoring filter.



#### NdisFilterTypeModifying = 2

A modifying filter.


### -field FilterRunType

The runtime attachment priority type for the filter. This type must be one of the following
     values:
     





#### NdisFilterRunTypeMandatory = 1

A mandatory filter. If the filter does not attach to the driver stack, NDIS will tear down the
       rest of the stack.



#### NdisFilterRunTypeOptional = 2

An optional filter. If the filter does not attach to the driver stack, NDIS will not tear down the
       rest of the stack.


### -field IfIndex

The NDIS interface index of the filter module.


### -field NetLuid

The 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> value that is assigned to the filter
     module. The NET_LUID is equivalent to the interface name (ifName in 
     RFC 2863).


### -field FilterClass

A UNICODE string that specifies the filter class. This string is the same as the 
     <b>FilterClass</b> INF file entry.


### -field FilterInstanceName

The filter instance name.


## -remarks



The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisenumeratefiltermodules">
    NdisEnumerateFilterModules</a> function returns one NDIS_FILTER_INTERFACE structure for each filter in
    the driver stack. The 
    <b>Flags</b> member identifies the filter as an NDIS 5.1 or earlier filter intermediate driver or an NDIS
    6.0 or later NDIS filter module.

A light-weight filter may dynamically insert or remove itself from the send or receive path by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfrestartfilter">NdisFRestartFilter</a> and providing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_filter_partial_characteristics">NDIS_FILTER_PARTIAL_CHARACTERISTICS</a> structure to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisenumeratefiltermodules">NdisEnumerateFilterModules</a>
 

 

