---
UID: NS:1394._ADDRESS_RANGE
title: "_ADDRESS_RANGE"
author: windows-driver-content
description: The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.
old-location: ieee\address_range.htm
old-project: IEEE
ms.assetid: 4eeb543b-0c23-4119-8e42-ff086b4b7682
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PADDRESS_RANGE, 1394/PADDRESS_RANGE, PADDRESS_RANGE, 1394/ADDRESS_RANGE, ADDRESS_RANGE, ADDRESS_RANGE structure [Buses], _ADDRESS_RANGE, 1394stct_e03538df-3b91-483d-99da-95645f017bef.xml, PADDRESS_RANGE structure pointer [Buses], IEEE.address_range"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	ADDRESS_RANGE
product: Windows
targetos: Windows
req.typenames: ADDRESS_RANGE, *PADDRESS_RANGE
---

# _ADDRESS_RANGE structure


## -description


The ADDRESS_RANGE structure describes a range in a IEEE 1394 device's address space.


## -syntax


````
typedef struct _ADDRESS_RANGE {
  USHORT AR_Off_High;
  USHORT AR_Length;
  ULONG  AR_Off_Low;
} ADDRESS_RANGE, *PADDRESS_RANGE;
````


## -struct-fields




### -field AR_Off_High

Specifies the high order bits of the 1394 address within the buffer.


### -field AR_Length

Specifies the length, in bytes, of a 1394 address buffer.


### -field AR_Off_Low

Specifies the low order bits of the 1394 address within the buffer.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537640">REQUEST_FREE_ADDRESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20ADDRESS_RANGE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

