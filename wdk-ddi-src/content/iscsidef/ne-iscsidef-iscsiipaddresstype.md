---
UID: NE:iscsidef.ISCSIIPADDRESSTYPE
title: ISCSIIPADDRESSTYPE (iscsidef.h)
description: The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.
old-location: storage\iscsiipaddresstype.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ISCSIIPADDRESSTYPE enumeration"]
ms.keywords: "*PISCSIIPADDRESSTYPE, ISCSIIPADDRESSTYPE, ISCSIIPADDRESSTYPE enumeration [Storage Devices], ISCSI_IP_ADDRESS_EMPTY, ISCSI_IP_ADDRESS_IPV4, ISCSI_IP_ADDRESS_IPV6, ISCSI_IP_ADDRESS_TEXT, PISCSIIPADDRESSTYPE, PISCSIIPADDRESSTYPE enumeration pointer [Storage Devices], iscsidef/ISCSIIPADDRESSTYPE, iscsidef/ISCSI_IP_ADDRESS_EMPTY, iscsidef/ISCSI_IP_ADDRESS_IPV4, iscsidef/ISCSI_IP_ADDRESS_IPV6, iscsidef/ISCSI_IP_ADDRESS_TEXT, iscsidef/PISCSIIPADDRESSTYPE, storage.iscsiipaddresstype, structs-iSCSI_3e947807-84e7-4886-aae9-95b8d1b508ab.xml"
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
targetos: Windows
req.typenames: ISCSIIPADDRESSTYPE, *PISCSIIPADDRESSTYPE
f1_keywords:
 - PISCSIIPADDRESSTYPE
 - iscsidef/PISCSIIPADDRESSTYPE
 - ISCSIIPADDRESSTYPE
 - iscsidef/ISCSIIPADDRESSTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsidef.h
api_name:
 - PISCSIIPADDRESSTYPE
 - ISCSIIPADDRESSTYPE
---

# ISCSIIPADDRESSTYPE enumeration


## -description

The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address.

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

<a href="/windows-hardware/drivers/ddi/iscsidef/ns-iscsidef-_iscsi_ip_address">ISCSI_IP_Address</a>

