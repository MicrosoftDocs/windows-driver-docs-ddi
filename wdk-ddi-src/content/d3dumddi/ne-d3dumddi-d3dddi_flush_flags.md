---
UID: NE:d3dumddi.D3DDDI_FLUSH_FLAGS
title: D3DDDI_FLUSH_FLAGS
author: windows-driver-content
description: In calls to the pfnFlush1 function, indicates whether the driver should free as much memory as possible. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddi_flush_flags.htm
old-project: display
ms.assetid: FE5EF59E-3B37-4947-A7E8-5CBE6137D07D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_FLUSH_FLAGS, display.d3dddi_flush_flags, D3DDDI_TRIM_MEMORY, d3dumddi/D3DDDI_FLUSH_FLAGS, d3dumddi/D3DDDI_TRIM_MEMORY, D3DDDI_FLUSH_FLAGS enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDI_FLUSH_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_FLUSH_FLAGS
---

# D3DDDI_FLUSH_FLAGS enumeration


## -description


In calls to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush1.md">pfnFlush1</a> function,  indicates whether the driver should free as much memory as possible. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -syntax


````
typedef enum _D3DDDI_FLUSH_FLAGS { 
  D3DDDI_TRIM_MEMORY  = 0x00000002
} D3DDDI_FLUSH_FLAGS;
````


## -enum-fields




### -field D3DDDI_TRIM_MEMORY

The driver should free as much memory as it can. However, it should not free any memory that the driver requires to continue operating. Using this constant value therefore should not introduce new opportunities to run out of memory.

The driver must no longer call <a href="https://msdn.microsoft.com/8BB6A7A3-E102-4069-BFC2-9605DDE9F020">Video memory offer and reclaim</a> DDIs on the memory that it frees.

Supported starting with Windows 8.1.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush1.md">pfnFlush1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_FLUSH_FLAGS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

