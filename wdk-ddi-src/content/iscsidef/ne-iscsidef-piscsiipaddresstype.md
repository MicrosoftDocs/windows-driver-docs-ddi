---
UID: NE:iscsidef.PISCSIIPADDRESSTYPE
title: "*PISCSIIPADDRESSTYPE"
author: windows-driver-content
description: The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.
old-location: storage\iscsiipaddresstype.htm
tech.root: storage
ms.assetid: a92f7048-ca8a-450c-93ab-6ea040412198
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PISCSIIPADDRESSTYPE, ISCSIIPADDRESSTYPE, ISCSIIPADDRESSTYPE enumeration [Storage Devices], ISCSI_IP_ADDRESS_EMPTY, ISCSI_IP_ADDRESS_IPV4, ISCSI_IP_ADDRESS_IPV6, ISCSI_IP_ADDRESS_TEXT, PISCSIIPADDRESSTYPE, PISCSIIPADDRESSTYPE enumeration pointer [Storage Devices], iscsidef/ISCSIIPADDRESSTYPE, iscsidef/ISCSI_IP_ADDRESS_EMPTY, iscsidef/ISCSI_IP_ADDRESS_IPV4, iscsidef/ISCSI_IP_ADDRESS_IPV6, iscsidef/ISCSI_IP_ADDRESS_TEXT, iscsidef/PISCSIIPADDRESSTYPE, storage.iscsiipaddresstype, structs-iSCSI_3e947807-84e7-4886-aae9-95b8d1b508ab.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsidef.h
api_name:
-	ISCSIIPADDRESSTYPE
product:
- Windows
targetos: Windows
req.typenames: ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE
---

# *PISCSIIPADDRESSTYPE enumeration


## -description


The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.


## -syntax


```cpp
typedef enum  {
  ISCSI_IP_ADDRESS_TEXT   = 0,
  ISCSI_IP_ADDRESS_IPV4   = 1,
  ISCSI_IP_ADDRESS_IPV6   = 2,
  ISCSI_IP_ADDRESS_EMPTY  = 3
} ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE;
```


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



 

 


