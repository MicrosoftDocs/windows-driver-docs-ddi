---
UID: NS:winspool._BIDI_REQUEST_CONTAINER
title: _BIDI_REQUEST_CONTAINER (winspool.h)
description: The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests.
old-location: print\bidi_request_container.htm
tech.root: print
ms.assetid: 9892cf0e-23ee-496f-9078-4a2a1fdb19d9
ms.date: 04/20/2018
ms.keywords: "*LPBIDI_REQUEST_CONTAINER, *PBIDI_REQUEST_CONTAINER, BIDI_REQUEST_CONTAINER, BIDI_REQUEST_CONTAINER structure [Print Devices], LPBIDI_REQUEST_CONTAINER, LPBIDI_REQUEST_CONTAINER structure pointer [Print Devices], PBIDI_REQUEST_CONTAINER, PBIDI_REQUEST_CONTAINER structure pointer [Print Devices], _BIDI_REQUEST_CONTAINER, print.bidi_request_container, spoolfnc_26c43d0f-69f8-415c-8653-79ef503fe139.xml, winspool/BIDI_REQUEST_CONTAINER, winspool/LPBIDI_REQUEST_CONTAINER, winspool/PBIDI_REQUEST_CONTAINER"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winspool.h
api_name:
- BIDI_REQUEST_CONTAINER
product:
- Windows
targetos: Windows
req.typenames: BIDI_REQUEST_CONTAINER, *PBIDI_REQUEST_CONTAINER, *LPBIDI_REQUEST_CONTAINER
---

# _BIDI_REQUEST_CONTAINER structure


## -description


The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests.


## -struct-fields




### -field Version

Specifies the version of the bidi API Schema, which is currently 1.


### -field Flags

Is a set of flags reserved for system use. This must be zero.


### -field Count

Specifies the number of bidi requests in the <b>aData</b> member. A container can contain zero or more requests, although a value of zero is valid only if the action is BIDI_ACTION_ENUM_SCHEMA.


### -field aData

Is an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winspool/ns-winspool-_bidi_request_data">BIDI_REQUEST_DATA</a> structures, each holding a single bidi request. 


## -remarks



Even though the <b>aData</b> member of this structure is an array with only a single array element, <b>aData</b>[0] should be thought of as the first element of an array of (possibly) an arbitrarily large size. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winspool/ns-winspool-_bidi_request_data">BIDI_REQUEST_DATA</a>
 

 

