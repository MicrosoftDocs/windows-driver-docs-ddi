---
UID: NS:hbaapi.HBA_ipaddress
title: HBA_ipaddress
author: windows-driver-content
description: The HBA_ipaddress structure specifies an IP address in a way that is independent of the version of the IP protocol in use.
old-location: storage\hba_ipaddress.htm
old-project: storage
ms.assetid: c3f79350-29e8-4e31-a31d-359c9781777d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_ipaddress, *PHBA_IPADDRESS, HBA_IPADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_IPADDRESS
req.alt-loc: hbaapi.h
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
req.typenames: *PHBA_IPADDRESS, HBA_IPADDRESS
---

# HBA_ipaddress structure



## -description
The HBA_ipaddress structure specifies an IP address in a way that is independent of the version of the IP protocol in use. 



## -syntax

````
typedef struct HBA_ipaddress {
  int   ipversion;
  union {
    unsigned char ipv4address[4];
    unsigned char ipv6address[16];
  } ipaddress;
} HBA_IPADDRESS, *PHBA_IPADDRESS;
````


## -struct-fields

### -field ipversion

Indicates the version of the IP protocol in use. 


### -field ipaddress


### -field ipv4address

Contains a dotted decimal IP4 address if version 4 of the IP protocol is in use. 


### -field ipv6address

Contains a dotted decimal IP6 address if version 6 of the IP protocol is in use. 

</dd>
</dl>

## -remarks
