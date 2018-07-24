---
UID: NS:winspool._BIDI_REQUEST_DATA
title: "_BIDI_REQUEST_DATA"
author: windows-driver-content
description: The BIDI_REQUEST_DATA structure holds a single bidi request.
old-location: print\bidi_request_data.htm
tech.root: print
ms.assetid: ef5a89e3-f072-48a7-b2d9-d68e0e27ba9e
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: "*LPBIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, BIDI_REQUEST_DATA, BIDI_REQUEST_DATA structure [Print Devices], LPBIDI_REQUEST_DATA, LPBIDI_REQUEST_DATA structure pointer [Print Devices], PBIDI_REQUEST_DATA, PBIDI_REQUEST_DATA structure pointer [Print Devices], _BIDI_REQUEST_DATA, print.bidi_request_data, spoolfnc_ab7c70f5-9161-4245-8f25-350f68144f82.xml, winspool/BIDI_REQUEST_DATA, winspool/LPBIDI_REQUEST_DATA, winspool/PBIDI_REQUEST_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winspool.h
api_name:
-	BIDI_REQUEST_DATA
product:
- Windows
targetos: Windows
req.typenames: BIDI_REQUEST_DATA, *PBIDI_REQUEST_DATA, *LPBIDI_REQUEST_DATA
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

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545177">BIDI_DATA</a> structure containing the data associated with the schema.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545177">BIDI_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545193">BIDI_REQUEST_CONTAINER</a>
 

 

