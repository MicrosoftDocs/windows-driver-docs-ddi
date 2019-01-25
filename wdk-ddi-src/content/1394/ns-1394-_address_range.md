---
UID: NS:1394._ADDRESS_RANGE
title: "_ADDRESS_RANGE" (1394.h)
description: The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.
old-location: ieee\address_range.htm
tech.root: IEEE
ms.assetid: 4eeb543b-0c23-4119-8e42-ff086b4b7682
ms.date: 02/15/2018
ms.keywords: "*PADDRESS_RANGE, 1394/ADDRESS_RANGE, 1394/PADDRESS_RANGE, 1394stct_e03538df-3b91-483d-99da-95645f017bef.xml, ADDRESS_RANGE, ADDRESS_RANGE structure [Buses], IEEE.address_range, PADDRESS_RANGE, PADDRESS_RANGE structure pointer [Buses], _ADDRESS_RANGE"
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
-	ADDRESS_RANGE
product:
- Windows
targetos: Windows
req.typenames: ADDRESS_RANGE, *PADDRESS_RANGE
---

# _ADDRESS_RANGE structure


## -description


The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.


## -struct-fields




### -field AR_Off_High

Specifies the high order bits of the 1394 address within the buffer.


### -field AR_Length

Specifies the length, in bytes, of a 1394 address buffer.


### -field AR_Off_Low

Specifies the low order bits of the 1394 address within the buffer.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537640">REQUEST_FREE_ADDRESS_RANGE</a>
 

 

