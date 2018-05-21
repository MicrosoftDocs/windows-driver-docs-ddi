---
UID: NF:winsplp.RouterFreeBidiMem
title: RouterFreeBidiMem function
author: windows-driver-content
description: RouterFreeBidiMem frees a block of memory that was previously allocated by RouterAllocBidiMem.
old-location: print\routerfreebidimem.htm
old-project: print
ms.assetid: 946b1630-844a-43ac-8c26-fdfa2ee7866a
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: RouterFreeBidiMem, RouterFreeBidiMem function [Print Devices], print.routerfreebidimem, spoolfnc_cc4cfcb8-c020-4112-9774-a2961e8a4ba2.xml, winsplp/RouterFreeBidiMem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	RouterFreeBidiMem
product:
- Windows
targetos: Windows
req.typenames: 
---

# RouterFreeBidiMem function


## -description


<code>RouterFreeBidiMem</code> frees a block of memory that was previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff561996">RouterAllocBidiMem</a>.


## -parameters




### -param pMemPointer [in]

Pointer to the memory to be freed.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561996">RouterAllocBidiMem</a>
 

 

