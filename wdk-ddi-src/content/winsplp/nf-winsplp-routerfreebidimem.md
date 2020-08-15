---
UID: NF:winsplp.RouterFreeBidiMem
title: RouterFreeBidiMem function (winsplp.h)
description: RouterFreeBidiMem frees a block of memory that was previously allocated by RouterAllocBidiMem.
old-location: print\routerfreebidimem.htm
tech.root: print
ms.assetid: 946b1630-844a-43ac-8c26-fdfa2ee7866a
ms.date: 04/20/2018
keywords: ["RouterFreeBidiMem function"]
ms.keywords: RouterFreeBidiMem, RouterFreeBidiMem function [Print Devices], print.routerfreebidimem, spoolfnc_cc4cfcb8-c020-4112-9774-a2961e8a4ba2.xml, winsplp/RouterFreeBidiMem
f1_keywords:
 - "winsplp/RouterFreeBidiMem"
 - "RouterFreeBidiMem"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in Windows XP and later operating systems.
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Spoolss.dll
api_name:
- RouterFreeBidiMem
targetos: Windows
req.typenames: 
---

# RouterFreeBidiMem function


## -description


<code>RouterFreeBidiMem</code> frees a block of memory that was previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidimem">RouterAllocBidiMem</a>.


## -parameters




### -param pMemPointer 
[in]
Pointer to the memory to be freed.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidimem">RouterAllocBidiMem</a>
 

 

