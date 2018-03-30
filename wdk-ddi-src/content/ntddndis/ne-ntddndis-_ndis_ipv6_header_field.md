---
UID: NE:ntddndis._NDIS_IPV6_HEADER_FIELD
title: "_NDIS_IPV6_HEADER_FIELD"
author: windows-driver-content
description: The NDIS_IPV6_HEADER_FIELD enumeration identifies the type of a field in an IP version 6 (IPv6) header to be filtered.
old-location: netvista\ndis_ipv6_header_field.htm
old-project: netvista
ms.assetid: 753BBA25-B0D5-4EBC-BA47-07ABEBCBA47D
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_IPV6_HEADER_FIELD, NDIS_IPV6_HEADER_FIELD, NDIS_IPV6_HEADER_FIELD enumeration [Network Drivers Starting with Windows Vista], NdisIPv6HeaderFieldMaximum, NdisIPv6HeaderFieldProtocol, NdisIPv6HeaderFieldUndefined, PNDIS_IPV6_HEADER_FIELD, PNDIS_IPV6_HEADER_FIELD enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_IPV6_HEADER_FIELD, netvista.ndis_ipv6_header_field, ntddndis/NDIS_IPV6_HEADER_FIELD, ntddndis/NdisIPv6HeaderFieldMaximum, ntddndis/NdisIPv6HeaderFieldProtocol, ntddndis/NdisIPv6HeaderFieldUndefined, ntddndis/PNDIS_IPV6_HEADER_FIELD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_IPV6_HEADER_FIELD
product: Windows
targetos: Windows
req.typenames: NDIS_IPV6_HEADER_FIELD, *PNDIS_IPV6_HEADER_FIELD
---

# _NDIS_IPV6_HEADER_FIELD enumeration


## -description


The <b>NDIS_IPV6_HEADER_FIELD</b> enumeration identifies the type of a field in an IP version 6 (IPv6) header to be filtered.


## -enum-fields




### -field NdisIPv6HeaderFieldUndefined

An undefined IPv6 header field.


### -field NdisIPv6HeaderFieldProtocol

The IPv6 protocol field.


### -field NdisIPv6HeaderFieldMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The <b>NDIS_IPV6_HEADER_FIELD</b> enumeration is used in the 
    <a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/3d387fe9-a7cc-4034-b31e-ba1359db2ae1">
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPV6_HEADER_FIELD enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
