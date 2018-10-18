---
UID: NS:1394._ADDRESS_OFFSET
title: "_ADDRESS_OFFSET"
author: windows-driver-content
description: The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.
old-location: ieee\address_offset.htm
tech.root: IEEE
ms.assetid: e1ee536f-40e4-48b7-b2d0-6ead22520ec8
ms.date: 2/15/2018
ms.keywords: "*PADDRESS_OFFSET, 1394/ADDRESS_OFFSET, 1394/PADDRESS_OFFSET, 1394stct_7b2efd3c-fcd3-4a01-8ece-8a70975787b1.xml, ADDRESS_OFFSET, ADDRESS_OFFSET structure [Buses], IEEE.address_offset, PADDRESS_OFFSET, PADDRESS_OFFSET structure pointer [Buses], _ADDRESS_OFFSET"
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
api_name:
-	ADDRESS_OFFSET
product:
- Windows
targetos: Windows
req.typenames: ADDRESS_OFFSET, *PADDRESS_OFFSET
---

# _ADDRESS_OFFSET structure


## -description


The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.


## -struct-fields




### -field Off_High

Specifies the high order offset for a IEEE 1394 address.


### -field Off_Low

Specifies the low order offset for a IEEE 1394 address.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537155">GET_LOCAL_HOST_INFO6</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537346">IO_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>
 

 

