---
UID: NF:winsplp.RouterAllocBidiResponseContainer
title: RouterAllocBidiResponseContainer function (winsplp.h)
description: RouterAllocBidiResponseContainer allocates a BIDI_RESPONSE_CONTAINER structure containing a list of bidi responses. The bidi response list is an array of BIDI_RESPONSE_DATA structures.
tech.root: print
ms.date: 07/27/2022
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

## -description

**RouterAllocBidiResponseContainer** allocates a [BIDI_RESPONSE_CONTAINER](../winspool/ns-winspool-_bidi_response_container.md) structure containing a list of bidi responses. The bidi response list is an array of [BIDI_RESPONSE_DATA](../winspool/ns-winspool-_bidi_response_data.md) structures.

## -parameters

### -param Count

Specifies the number of BIDI_RESPONSE_DATA structures to be allocated.

## -returns

**RouterAllocBidiResponseContainer** returns a pointer to the allocated structure, on success. If the function fails to allocate the structure, the caller can obtain the error code from **GetLastError**.

## -remarks

When the memory allocated by this function is no longer needed, use [RouterFreeBidiResponseContainer](./nf-winsplp-routerfreebidiresponsecontainer.md).

## -see-also

[BIDI_RESPONSE_CONTAINER](../winspool/ns-winspool-_bidi_response_container.md)

[BIDI_RESPONSE_DATA](../winspool/ns-winspool-_bidi_response_data.md)

[RouterFreeBidiResponseContainer](./nf-winsplp-routerfreebidiresponsecontainer.md)

[SendRecvBidiDataFromPort](/previous-versions/ff562071(v=vs.85))