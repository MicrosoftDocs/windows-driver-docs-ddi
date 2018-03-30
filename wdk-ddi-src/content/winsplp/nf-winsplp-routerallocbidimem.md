---
UID: NF:winsplp.RouterAllocBidiMem
title: RouterAllocBidiMem function
author: windows-driver-content
description: RouterAllocBidiMem allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.
old-location: print\routerallocbidimem.htm
old-project: print
ms.assetid: 39042c66-3db1-41bd-b06d-12aefcb007d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RouterAllocBidiMem, RouterAllocBidiMem function [Print Devices], print.routerallocbidimem, spoolfnc_ed433d21-ccfa-4061-9fbd-3bf333e12b31.xml, winsplp/RouterAllocBidiMem
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
-	RouterAllocBidiMem
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# RouterAllocBidiMem function


## -description


<code>RouterAllocBidiMem</code> allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.


## -parameters




### -param NumBytes [in]

Specifies the size, in bytes, of the block of memory to be allocated.


## -returns



<code>RouterAllocBidiMem</code> returns a pointer to the block of memory if successful. If the function fails, the caller can obtain the error code by calling <b>GetLastError</b> (described in the Microsoft Windows SDK documentation).




## -remarks



When the memory allocated by this function is no longer needed, it can be returned by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562012">RouterFreeBidiMem</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562012">RouterFreeBidiMem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562071">SendRecvBidiDataFromPort</a>
 

 

