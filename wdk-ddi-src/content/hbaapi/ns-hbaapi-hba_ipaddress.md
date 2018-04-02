---
UID: NS:hbaapi.HBA_ipaddress
title: HBA_ipaddress
author: windows-driver-content
description: The HBA_ipaddress structure specifies an IP address in a way that is independent of the version of the IP protocol in use.
old-location: storage\hba_ipaddress.htm
old-project: storage
ms.assetid: c3f79350-29e8-4e31-a31d-359c9781777d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_IPADDRESS, HBA_IPADDRESS, HBA_IPADDRESS structure [Storage Devices], HBA_ipaddress, HBA_ipaddress structure [Storage Devices], PHBA_IPADDRESS, PHBA_IPADDRESS structure pointer [Storage Devices], hbaapi/HBA_ipaddress, hbaapi/PHBA_IPADDRESS, storage.hba_ipaddress, structs-Fibre_8ac1972d-ec33-4642-8dfe-3d913913ca66.xml"
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
-	hbaapi.h
api_name:
-	HBA_IPADDRESS
product: Windows
targetos: Windows
req.typenames: HBA_IPADDRESS, *PHBA_IPADDRESS
---

# HBA_ipaddress structure


## -description


The HBA_ipaddress structure specifies an IP address in a way that is independent of the version of the IP protocol in use. 


## -struct-fields




### -field ipversion

Indicates the version of the IP protocol in use. 


### -field ipaddress



#### ipv4address

Contains a dotted decimal IP4 address if version 4 of the IP protocol is in use. 



#### ipv6address

Contains a dotted decimal IP6 address if version 6 of the IP protocol is in use. 

