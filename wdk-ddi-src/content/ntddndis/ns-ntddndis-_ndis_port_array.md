---
UID: NS:ntddndis._NDIS_PORT_ARRAY
title: "_NDIS_PORT_ARRAY"
author: windows-driver-content
description: The NDIS_PORT_ARRAY structure specifies a list of NDIS ports and their associated characteristics.
old-location: netvista\ndis_port_array.htm
old-project: netvista
ms.assetid: f77469d3-ce48-4e17-9fff-1af56296f61f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NDIS_PORT_ARRAY, NDIS_PORT_ARRAY, *PNDIS_PORT_ARRAY, PNDIS_PORT_ARRAY, PNDIS_PORT_ARRAY structure pointer [Network Drivers Starting with Windows Vista], ndis_ports_ref_1bba9fc6-0cd9-40f7-92ad-20979dcaa400.xml, NDIS_PORT_ARRAY structure [Network Drivers Starting with Windows Vista], _NDIS_PORT_ARRAY, netvista.ndis_port_array, ntddndis/PNDIS_PORT_ARRAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_PORT_ARRAY
product: Windows
targetos: Windows
req.typenames: "*PNDIS_PORT_ARRAY, NDIS_PORT_ARRAY"
---

# _NDIS_PORT_ARRAY structure


## -description


The NDIS_PORT_ARRAY structure specifies a list of NDIS ports and their associated
  characteristics.


## -syntax


````
typedef struct _NDIS_PORT_ARRAY {
  NDIS_OBJECT_HEADER        Header;
  ULONG                     NumberOfPorts;
  ULONG                     OffsetFirstPort;
  ULONG                     ElementSize;
  NDIS_PORT_CHARACTERISTICS Ports[1];
} NDIS_PORT_ARRAY, *PNDIS_PORT_ARRAY;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PORT_ARRAY structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_ARRAY_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_ARRAY_REVISION_1.


### -field NumberOfPorts

The number of NDIS ports that have characteristics that are listed in the 
     <b>Ports</b> member.


### -field OffsetFirstPort

The offset, in bytes, from the beginning of the NDIS_PORT_ARRAY structure to the start of the
     first port characteristics data.


### -field ElementSize

The size, in bytes, of each element in the array that the 
     <b>Ports</b> member specifies.


### -field Ports

An array that contains the port characteristics for each active NDIS port on a miniport adapter.
     The 
     <b>ElementSize</b> member specifies the size of each element in the array. The 
     <b>NumberOfPorts</b> member specifies the number of elements in the array. Each
     element in the array is an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
     NDIS_PORT_CHARACTERISTICS</a> structure.


## -remarks


The NDIS_PORT_ARRAY structure specifies characteristics, of all of the active NDIS ports on the
    miniport adapter, for the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a> OID.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT_ARRAY structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

