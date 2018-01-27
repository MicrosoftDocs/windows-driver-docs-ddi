---
UID: NS:wwan._WWAN_IPV4_ADDRESS
title: _WWAN_IPV4_ADDRESS
author: windows-driver-content
description: The WWAN_IPV4_ADDRESS structure represents an IPV4 address of a PDP context.
old-location: netvista\wwan_ipv4_address.htm
old-project: netvista
ms.assetid: D75EAC9E-8E65-437E-83AA-59B422527C6C
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_IPV4_ADDRESS, wwan/WWAN_IPV4_ADDRESS, PWWAN_IPV4_ADDRESS, PWWAN_IPV4_ADDRESS structure pointer [Network Drivers Starting with Windows Vista], _WWAN_IPV4_ADDRESS, netvista.wwan_ipv4_address, *PWWAN_IPV4_ADDRESS, WWAN_IPV4_ADDRESS structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_IPV4_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
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
-	wwan.h
apiname: 
-	WWAN_IPV4_ADDRESS
product: Windows
targetos: Windows
req.typenames: *PWWAN_IPV4_ADDRESS, WWAN_IPV4_ADDRESS
req.product: Windows 10 or later.
---

# _WWAN_IPV4_ADDRESS structure


## -description


The WWAN_IPV4_ADDRESS structure represents an IPV4 address of a PDP context.


## -syntax


````
typedef struct _WWAN_IPV4_ADDRESS {
  ULONG OnLinkPrefixLength;
  UCHAR IPV4Address[4];
} WWAN_IPV4_ADDRESS, *PWWAN_IPV4_ADDRESS;
````


## -struct-fields




### -field OnLinkPrefixLength

The length of the prefix or network part of the IP address of the PDP context.


### -field IPV4Address

 



#### - IPV4Address[4]

The IPV4 address of the PDP context.

