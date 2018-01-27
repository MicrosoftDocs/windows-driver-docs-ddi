---
UID: NE:iscsidef.PISCSIIPADDRESSTYPE
title: *PISCSIIPADDRESSTYPE
author: windows-driver-content
description: The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.
old-location: storage\iscsiipaddresstype.htm
old-project: storage
ms.assetid: a92f7048-ca8a-450c-93ab-6ea040412198
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PISCSIIPADDRESSTYPE enumeration pointer [Storage Devices], ISCSI_IP_ADDRESS_IPV6, iscsidef/ISCSI_IP_ADDRESS_IPV6, ISCSI_IP_ADDRESS_IPV4, iscsidef/ISCSI_IP_ADDRESS_TEXT, ISCSI_IP_ADDRESS_TEXT, structs-iSCSI_3e947807-84e7-4886-aae9-95b8d1b508ab.xml, ISCSIIPADDRESSTYPE, ISCSI_IP_ADDRESS_EMPTY, storage.iscsiipaddresstype, ISCSIIPADDRESSTYPE enumeration [Storage Devices], iscsidef/ISCSI_IP_ADDRESS_IPV4, PISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE, iscsidef/ISCSIIPADDRESSTYPE, iscsidef/ISCSI_IP_ADDRESS_EMPTY, iscsidef/PISCSIIPADDRESSTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	ISCSIIPADDRESSTYPE
product: Windows
targetos: Windows
req.typenames: ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE
---

# *PISCSIIPADDRESSTYPE enumeration


## -description


The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.


## -syntax


````
typedef enum  { 
  ISCSI_IP_ADDRESS_TEXT   = 0,
  ISCSI_IP_ADDRESS_IPV4   = 1,
  ISCSI_IP_ADDRESS_IPV6   = 2,
  ISCSI_IP_ADDRESS_EMPTY  = 3
} ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE;
````


## -enum-fields




### -field ISCSI_IP_ADDRESS_TEXT

The IP address is in dotted decimal text format or in DNS format.


### -field ISCSI_IP_ADDRESS_IPV4

The IP address is a binary address that complies with version 4 of the IP protocol.


### -field ISCSI_IP_ADDRESS_IPV6

The IP address is a binary address that complies with version 6 of the IP protocol.


### -field ISCSI_IP_ADDRESS_EMPTY

No address is specified.


## -see-also

<a href="..\iscsidef\ns-iscsidef-_iscsi_ip_address.md">ISCSI_IP_Address</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSIIPADDRESSTYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

