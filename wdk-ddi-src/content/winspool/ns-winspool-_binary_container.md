---
UID: NS:winspool._BINARY_CONTAINER
title: "_BINARY_CONTAINER"
author: windows-driver-content
description: The BINARY_CONTAINER structure is a container for binary data.
old-location: print\binary_container.htm
old-project: print
ms.assetid: bac960c5-7c29-4550-9b82-5adb6a0cc243
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PBINARY_CONTAINER, BINARY_CONTAINER, BINARY_CONTAINER structure [Print Devices], PBINARY_CONTAINER, PBINARY_CONTAINER structure pointer [Print Devices], _BINARY_CONTAINER, print.binary_container, spoolfnc_a034cd3e-8afb-4a15-9640-06d693fd150c.xml, winspool/BINARY_CONTAINER, winspool/PBINARY_CONTAINER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later operating systems.
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
-	winspool.h
api_name:
-	BINARY_CONTAINER
product: Windows
targetos: Windows
req.typenames: BINARY_CONTAINER, *PBINARY_CONTAINER
req.product: Windows 10 or later.
---

# _BINARY_CONTAINER structure


## -description


The BINARY_CONTAINER structure is a container for binary data.


## -struct-fields




### -field cbBuf

Specifies the number of bytes of binary data in the <b>pData</b> member.


### -field pData

Pointer to a buffer that contains the binary data.


## -remarks



The BINARY_CONTAINER structure is used in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545177">BIDI_DATA</a> structure when the bidi data consists of binary data, as opposed to integer, float, or string data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545177">BIDI_DATA</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BINARY_CONTAINER structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

