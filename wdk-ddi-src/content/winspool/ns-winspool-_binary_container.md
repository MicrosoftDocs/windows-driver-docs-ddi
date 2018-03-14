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


## -syntax


````
typedef struct _BINARY_CONTAINER {
  DWORD  cbBuf;
  LPBYTE pData;
} BINARY_CONTAINER, *PBINARY_CONTAINER;
````


## -struct-fields




### -field cbBuf

Specifies the number of bytes of binary data in the <b>pData</b> member.


### -field pData

Pointer to a buffer that contains the binary data.


## -remarks



The BINARY_CONTAINER structure is used in a <a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a> structure when the bidi data consists of binary data, as opposed to integer, float, or string data.




## -see-also

<a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a>



 

 


