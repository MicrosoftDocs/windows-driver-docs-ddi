---
UID: NS:iscsidef._ISCSI_IP_Address
title: "_ISCSI_IP_Address"
author: windows-driver-content
description: The ISCSI_IP_Address structure defines an IP address.
old-location: storage\iscsi_ip_address.htm
old-project: storage
ms.assetid: ec4c2add-33e0-4e3d-8f19-892cca4720a7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PISCSI_IP_Address, ISCSI_IP_Address, ISCSI_IP_Address structure [Storage Devices], PISCSI_IP_Address, PISCSI_IP_Address structure pointer [Storage Devices], _ISCSI_IP_Address, iscsidef/ISCSI_IP_Address, iscsidef/PISCSI_IP_Address, storage.iscsi_ip_address, structs-iSCSI_c8f7a419-6398-4ece-a92d-fc0deffbe39a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	iscsidef.h
api_name:
-	ISCSI_IP_Address
product:
- Windows
targetos: Windows
req.typenames: ISCSI_IP_Address, *PISCSI_IP_Address
---

# _ISCSI_IP_Address structure


## -description


The ISCSI_IP_Address structure defines an IP address.


## -struct-fields




### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561482">ISCSIIPADDRESSTYPE</a> value that indicates the type of IP address. 


### -field IpV4Address

If <b>Type</b> = <b>ISCSI_IP_ADDRESS_IPV4</b>, the binary version 4 IP address. Otherwise, <b>IpV4Address</b> is not defined.


### -field IpV6Address

If <b>Type</b> = <b>ISCSI_IP_ADDRESS_IPV6</b>, the binary version 6 IP address. Otherwise, <b>IpV6Address</b> is not defined.


### -field IpV6FlowInfo

If <b>Type</b> = <b>ISCSI_IP_ADDRESS_IPV6</b>, the flow information for this IP address, as defined in version 6 of the IP protocol. Otherwise, <b>IpV6FlowInfo</b> is not defined.


### -field IpV6ScopeId

If <b>Type</b> = <b>ISCSI_IP_ADDRESS_IPV6</b>, the scope ID of this IP address, as defined in version 6 of the IP protocol,. Otherwise, <b>IpV6ScopeId</b> is not defined.


### -field TextAddress

If <b>Type</b> = <b>ISCSI_IP_ADDRESS_TEXT</b>, the DNS or dotted decimal text address. Otherwise, <b>TextAddress</b> is not defined.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561482">ISCSIIPADDRESSTYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561536">ISCSI_IP_Address</a>
 

 

