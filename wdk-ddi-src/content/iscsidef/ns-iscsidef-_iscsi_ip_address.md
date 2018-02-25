---
UID: NS:iscsidef._ISCSI_IP_Address
title: "_ISCSI_IP_Address"
author: windows-driver-content
description: The ISCSI_IP_Address structure defines an IP address.
old-location: storage\iscsi_ip_address.htm
old-project: storage
ms.assetid: ec4c2add-33e0-4e3d-8f19-892cca4720a7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PISCSI_IP_Address, ,, A, C, I, ISCSI_IP_Address, ISCSI_IP_Address structure [Storage Devices], P, PISCSI_IP_Address, PISCSI_IP_Address structure pointer [Storage Devices], S, _, _ISCSI_IP_Address, d, e, iscsidef/ISCSI_IP_Address, iscsidef/PISCSI_IP_Address, r, s, storage.iscsi_ip_address, structs-iSCSI_c8f7a419-6398-4ece-a92d-fc0deffbe39a.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsidef.h
apiname:
-	ISCSI_IP_Address
product: Windows
targetos: Windows
req.typenames: ISCSI_IP_Address, *PISCSI_IP_Address
---

# _ISCSI_IP_Address structure


## -description


The ISCSI_IP_Address structure defines an IP address.


## -syntax


````
typedef struct _ISCSI_IP_Address {
  ULONG Type;
  ULONG IpV4Address;
  UCHAR IpV6Address[16];
  ULONG IpV6FlowInfo;
  ULONG IpV6ScopeId;
  WCHAR TextAddress[256 + 1];
} ISCSI_IP_Address, *PISCSI_IP_Address;
````


## -struct-fields




### -field Type

A <a href="..\iscsidef\ne-iscsidef-piscsiipaddresstype.md">ISCSIIPADDRESSTYPE</a> value that indicates the type of IP address. 


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

<a href="..\iscsidef\ne-iscsidef-piscsiipaddresstype.md">ISCSIIPADDRESSTYPE</a>



<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_IP_Address structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

