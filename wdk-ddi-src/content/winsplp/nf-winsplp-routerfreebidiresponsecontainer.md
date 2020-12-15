---
UID: NF:winsplp.RouterFreeBidiResponseContainer
title: RouterFreeBidiResponseContainer function (winsplp.h)
description: RouterFreeBidiResponseContainer frees a BIDI_RESPONSE_CONTAINER structure previously allocated by RouterAllocBidiResponseContainer.
old-location: print\routerfreebidiresponsecontainer.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["RouterFreeBidiResponseContainer function"]
ms.keywords: RouterFreeBidiResponseContainer, RouterFreeBidiResponseContainer function [Print Devices], print.routerfreebidiresponsecontainer, spoolfnc_065c8a3a-5790-45f5-bf79-3af94fdd0571.xml, winsplp/RouterFreeBidiResponseContainer
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
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - RouterFreeBidiResponseContainer
 - winsplp/RouterFreeBidiResponseContainer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - RouterFreeBidiResponseContainer
---

# RouterFreeBidiResponseContainer function


## -description

<code>RouterFreeBidiResponseContainer</code> frees a <a href="/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_container">BIDI_RESPONSE_CONTAINER</a> structure previously allocated by <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidiresponsecontainer">RouterAllocBidiResponseContainer</a>.

## -parameters

### -param pData 

[in]
Pointer to the BIDI_RESPONSE_CONTAINER structure to be freed.

## -returns

<code>RouterFreeBidiResponseContainer</code> normally returns ERROR_SUCCESS, unless it throws an exception. In that case it returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_container">BIDI_RESPONSE_CONTAINER</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidiresponsecontainer">RouterAllocBidiResponseContainer</a>
