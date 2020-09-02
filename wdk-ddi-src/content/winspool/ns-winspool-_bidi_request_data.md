---
UID: NS:winspool._BIDI_REQUEST_DATA
title: _BIDI_REQUEST_DATA (winspool.h)
description: The BIDI_REQUEST_DATA structure holds a single bidi request.
old-location: print\bidi_request_data.htm
tech.root: print
ms.assetid: ef5a89e3-f072-48a7-b2d9-d68e0e27ba9e
ms.date: 04/20/2018
keywords: ["BIDI_REQUEST_DATA structure"]
ms.keywords: "*LPBIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, BIDI_REQUEST_DATA, BIDI_REQUEST_DATA structure [Print Devices], LPBIDI_REQUEST_DATA, LPBIDI_REQUEST_DATA structure pointer [Print Devices], PBIDI_REQUEST_DATA, PBIDI_REQUEST_DATA structure pointer [Print Devices], _BIDI_REQUEST_DATA, print.bidi_request_data, spoolfnc_ab7c70f5-9161-4245-8f25-350f68144f82.xml, winspool/BIDI_REQUEST_DATA, winspool/LPBIDI_REQUEST_DATA, winspool/PBIDI_REQUEST_DATA"
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later.
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
req.typenames: BIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, *LPBIDI_REQUEST_DATA
f1_keywords:
 - _BIDI_REQUEST_DATA
 - winspool/_BIDI_REQUEST_DATA
 - PBIDI_REQUEST_DATA
 - winspool/PBIDI_REQUEST_DATA
 - BIDI_REQUEST_DATA
 - winspool/BIDI_REQUEST_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winspool.h
api_name:
 - BIDI_REQUEST_DATA
---

# _BIDI_REQUEST_DATA structure


## -description

The BIDI_REQUEST_DATA structure holds a single bidi request.

## -struct-fields

### -field dwReqNumber

Specifies the index of the request, which is used to match a response with a request in a multirequest operation.

### -field pSchema

Pointer to a memory location containing the first byte of the schema string.

### -field data

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_data">BIDI_DATA</a> structure containing the data associated with the schema.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_data">BIDI_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winspool/ns-winspool-_bidi_request_container">BIDI_REQUEST_CONTAINER</a>

