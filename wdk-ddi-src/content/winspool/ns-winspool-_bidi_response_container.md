---
UID: NS:winspool._BIDI_RESPONSE_CONTAINER
title: _BIDI_RESPONSE_CONTAINER (winspool.h)
description: The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses.
old-location: print\bidi_response_container.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["BIDI_RESPONSE_CONTAINER structure"]
ms.keywords: "*LPBIDI_RESPONSE_CONTAINER, *PBIDI_RESPONSE_CONTAINER, BIDI_RESPONSE_CONTAINER, BIDI_RESPONSE_CONTAINER structure [Print Devices], LPBIDI_RESPONSE_CONTAINER, LPBIDI_RESPONSE_CONTAINER structure pointer [Print Devices], PBIDI_RESPONSE_CONTAINER, PBIDI_RESPONSE_CONTAINER structure pointer [Print Devices], _BIDI_RESPONSE_CONTAINER, print.bidi_response_container, spoolfnc_79e5354d-1fc1-4156-8be9-028ebcd14b16.xml, winspool/BIDI_RESPONSE_CONTAINER, winspool/LPBIDI_RESPONSE_CONTAINER, winspool/PBIDI_RESPONSE_CONTAINER"
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
targetos: Windows
req.typenames: BIDI_RESPONSE_CONTAINER, *PBIDI_RESPONSE_CONTAINER, *LPBIDI_RESPONSE_CONTAINER
f1_keywords:
 - _BIDI_RESPONSE_CONTAINER
 - winspool/_BIDI_RESPONSE_CONTAINER
 - PBIDI_RESPONSE_CONTAINER
 - winspool/PBIDI_RESPONSE_CONTAINER
 - BIDI_RESPONSE_CONTAINER
 - winspool/BIDI_RESPONSE_CONTAINER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winspool.h
api_name:
 - BIDI_RESPONSE_CONTAINER
---

# _BIDI_RESPONSE_CONTAINER structure


## -description

The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses.

## -struct-fields

### -field Version

Specifies the version of the bidi API Schema, which is currently 1.

### -field Flags

Is a set of flags reserved for system use. This must be zero.

### -field Count

Specifies the number of responses in the <b>aData</b> member.

### -field aData

Is an array of <a href="/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_data">BIDI_RESPONSE_DATA</a> structures, each containing a single bidi response.

## -remarks

Even though the <b>aData</b> member of this structure is an array with only a single array element, <b>aData</b>[0] should be thought of as the first element of an array of (possibly) an arbitrarily large size.

The spooler's <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidiresponsecontainer">RouterAllocBidiResponseContainer</a> function allocates the memory needed for this structure, which is then used to hold an array of BIDI_RESPONSE_DATA structures. When a BIDI_RESPONSE_CONTAINER structure is no longer needed, it should be freed by a call to <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidiresponsecontainer">RouterFreeBidiResponseContainer</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_response_data">BIDI_RESPONSE_DATA</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocbidiresponsecontainer">RouterAllocBidiResponseContainer</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreebidiresponsecontainer">RouterFreeBidiResponseContainer</a>
