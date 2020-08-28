---
UID: NF:winsplp.RouterAllocBidiMem
title: RouterAllocBidiMem function (winsplp.h)
description: RouterAllocBidiMem allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.
old-location: print\routerallocbidimem.htm
tech.root: print
ms.assetid: 39042c66-3db1-41bd-b06d-12aefcb007d3
ms.date: 04/20/2018
keywords: ["RouterAllocBidiMem function"]
ms.keywords: RouterAllocBidiMem, RouterAllocBidiMem function [Print Devices], print.routerallocbidimem, spoolfnc_ed433d21-ccfa-4061-9fbd-3bf333e12b31.xml, winsplp/RouterAllocBidiMem
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RouterAllocBidiMem
 - winsplp/RouterAllocBidiMem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - RouterAllocBidiMem
---

# RouterAllocBidiMem function


## -description

<code>RouterAllocBidiMem</code> allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects.

## -parameters

### -param NumBytes 

[in]
Specifies the size, in bytes, of the block of memory to be allocated.

## -returns

<code>RouterAllocBidiMem</code> returns a pointer to the block of memory if successful. If the function fails, the caller can obtain the error code by calling <b>GetLastError</b> (described in the Microsoft Windows SDK documentation).

## -remarks

When the memory allocated by this function is no longer needed, it can be returned by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidimem">RouterFreeBidiMem</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidimem">RouterFreeBidiMem</a>



<a href="https://docs.microsoft.com/previous-versions/ff562071(v=vs.85)">SendRecvBidiDataFromPort</a>

