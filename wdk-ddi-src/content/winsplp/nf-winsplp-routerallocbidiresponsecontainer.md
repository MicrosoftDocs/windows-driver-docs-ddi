---
UID: NF:winsplp.RouterAllocBidiResponseContainer
title: RouterAllocBidiResponseContainer function (winsplp.h)
description: RouterAllocBidiResponseContainer allocates a BIDI_RESPONSE_CONTAINER structure containing a list of bidi responses. The bidi response list is an array of BIDI_RESPONSE_DATA structures.
old-location: print\routerallocbidiresponsecontainer.htm
tech.root: print
ms.assetid: ca10f0d5-62d6-451a-96e5-38aca18cf5b0
ms.date: 04/20/2018
keywords: ["RouterAllocBidiResponseContainer function"]
ms.keywords: RouterAllocBidiResponseContainer, RouterAllocBidiResponseContainer function [Print Devices], print.routerallocbidiresponsecontainer, spoolfnc_05ba5d83-8913-4591-9ada-2e57440354b9.xml, winsplp/RouterAllocBidiResponseContainer
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
 - RouterAllocBidiResponseContainer
 - winsplp/RouterAllocBidiResponseContainer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - RouterAllocBidiResponseContainer
---

# RouterAllocBidiResponseContainer function


## -description

<code>RouterAllocBidiResponseContainer</code> allocates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_container">BIDI_RESPONSE_CONTAINER</a> structure containing a list of bidi responses. The bidi response list is an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_data">BIDI_RESPONSE_DATA</a> structures.

## -parameters

### -param Count

#### - cSize [in]

Specifies the number of BIDI_RESPONSE_DATA structures to be allocated.

## -returns

<code>RouterAllocBidiResponseContainer</code> returns a pointer to the allocated structure, on success. If the function fails to allocate the structure, the caller can obtain the error code from <b>GetLastError</b> (described in the Microsoft Windows SDK documentation).

## -remarks

When the memory allocated by this function is no longer needed, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidiresponsecontainer">RouterFreeBidiResponseContainer</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_container">BIDI_RESPONSE_CONTAINER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_data">BIDI_RESPONSE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidiresponsecontainer">RouterFreeBidiResponseContainer</a>



<a href="https://docs.microsoft.com/previous-versions/ff562071(v=vs.85)">SendRecvBidiDataFromPort</a>

