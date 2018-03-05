---
UID: NS:d3dumddi.D3DDDIARG_COPYFLAGS
title: D3DDDIARG_COPYFLAGS
author: windows-driver-content
description: Describes how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_copyflags.htm
old-project: display
ms.assetid: DA114D60-60EE-4D1D-B42C-A84CE54C8B95
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_COPYFLAGS, D3DDDIARG_COPYFLAGS structure [Display Devices], d3dumddi/D3DDDIARG_COPYFLAGS, display.d3dddiarg_copyflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
api_name:
-	D3DDDIARG_COPYFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_COPYFLAGS
---

# D3DDDIARG_COPYFLAGS structure


## -description


Describes how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -syntax


````
typedef struct D3DDDIARG_COPYFLAGS {
  union {
    struct {
      UINT NoOverwrite  :1;
      UINT Discard  :1;
      UINT Reserved1  :22;
      UINT BoxValid  :1;
      UINT Reserved2  :7;
    };
    UINT Value;
  };
} D3DDDIARG_COPYFLAGS;
````


## -struct-fields




### -field NoOverwrite

Specifies that the caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Discard

Specifies that the user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved1

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting bits 3 through 24 (0x00FFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field BoxValid

Specifies that a destination region of the subresource to be copied to is valid. When not set, the entire subresource must be updated.

Setting this member is equivalent to setting the twenty-fifth bit of the 32-bit <b>Value</b> member (0x01000000).


### -field Reserved2

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting bits 26 through 32 (0xFE000000) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that <b>D3DDDIARG_COPYFLAGS</b> contains that can hold a 32-bit value that identifies how to handle the existing contents of a resource during a copy or update operation.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_updatesubresourceup.md">D3DDDIARG_UPDATESUBRESOURCEUP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_COPYFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

