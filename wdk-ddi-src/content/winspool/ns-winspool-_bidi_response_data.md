---
UID: NS:winspool._BIDI_RESPONSE_DATA
title: "_BIDI_RESPONSE_DATA"
author: windows-driver-content
description: The BIDI_RESPONSE_DATA structure holds a single bidi response.
old-location: print\bidi_response_data.htm
old-project: print
ms.assetid: 8e56ef0a-c652-4fca-ad87-4a0495c8de2e
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: winspool/PBIDI_RESPONSE_DATA, BIDI_RESPONSE_DATA structure [Print Devices], PBIDI_RESPONSE_DATA structure pointer [Print Devices], BIDI_RESPONSE_DATA, *PBIDI_RESPONSE_DATA, PBIDI_RESPONSE_DATA, print.bidi_response_data, LPBIDI_RESPONSE_DATA structure pointer [Print Devices], winspool/BIDI_RESPONSE_DATA, LPBIDI_RESPONSE_DATA, spoolfnc_eb6aa91d-8fbc-4079-a8b8-57d5c3ff7abf.xml, _BIDI_RESPONSE_DATA, *LPBIDI_RESPONSE_DATA, winspool/LPBIDI_RESPONSE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winspool.h
apiname:
-	BIDI_RESPONSE_DATA
product: Windows
targetos: Windows
req.typenames: BIDI_RESPONSE_DATA, *PBIDI_RESPONSE_DATA, *LPBIDI_RESPONSE_DATA
req.product: Windows 10 or later.
---

# _BIDI_RESPONSE_DATA structure


## -description


The BIDI_RESPONSE_DATA structure holds a single bidi response.


## -syntax


````
typedef struct _BIDI_RESPONSE_DATA {
  DWORD     dwResult;
  DWORD     dwReqNumber;
  LPWSTR    pSchema;
  BIDI_DATA data;
} BIDI_RESPONSE_DATA, *PBIDI_RESPONSE_DATA, *LPBIDI_RESPONSE_DATA;
````


## -struct-fields




### -field dwResult

Specifies the last error of the response.


### -field dwReqNumber

Specifies a number used to match a response and a request in a multirequest operation.


### -field pSchema

Pointer to a memory location containing the first byte of the schema string.


### -field data

Specifies a <a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a> structure containing the data associated with the schema.


## -remarks


The spooler's <a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a> function is used to allocate the memory needed for a <a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a> structure, which is then used to hold an array of BIDI_RESPONSE_DATA structures. When a BIDI_RESPONSE_CONTAINER structure is no longer needed, it should be freed by a call to <a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>. 

When the bidi action is BIDI_ACTION_GETALL, the <b>dwReqNumber</b> member holds the ID of the matching request in the <a href="..\winspool\ns-winspool-_bidi_request_container.md">BIDI_REQUEST_CONTAINER</a> structure, the <b>pSchema</b> member points to the schema string associated with the data, and the <b>data</b> member holds the bidi data. If the bidi action is BIDI_ACTION_ENUM_SCHEMA, <b>pSchema</b> should be set to <b>NULL</b>, and the <b>data</b> member will hold the supported schema string. In this case, <b>data.dwDataType</b> is set to BIDI_TEXT (a <a href="..\winspool\ns-winspool-_bidi_data.md">BIDI_DATA</a> enumerator). For information about the BIDI_ACTION_<i>Xxx</i> constants, see IBidiSpooler::MultiSendRecv in the Microsoft Windows SDK documentation.



## -see-also

<a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a>

<a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>

<a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_RESPONSE_DATA structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

