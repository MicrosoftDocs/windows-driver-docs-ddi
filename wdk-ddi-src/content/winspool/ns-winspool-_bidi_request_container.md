---
UID: NS:winspool._BIDI_REQUEST_CONTAINER
title: "_BIDI_REQUEST_CONTAINER"
author: windows-driver-content
description: The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests.
old-location: print\bidi_request_container.htm
old-project: print
ms.assetid: 9892cf0e-23ee-496f-9078-4a2a1fdb19d9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: LPBIDI_REQUEST_CONTAINER, PBIDI_REQUEST_CONTAINER structure pointer [Print Devices], winspool/LPBIDI_REQUEST_CONTAINER, *PBIDI_REQUEST_CONTAINER, print.bidi_request_container, BIDI_REQUEST_CONTAINER, BIDI_REQUEST_CONTAINER structure [Print Devices], PBIDI_REQUEST_CONTAINER, *LPBIDI_REQUEST_CONTAINER, winspool/PBIDI_REQUEST_CONTAINER, winspool/BIDI_REQUEST_CONTAINER, LPBIDI_REQUEST_CONTAINER structure pointer [Print Devices], spoolfnc_26c43d0f-69f8-415c-8653-79ef503fe139.xml, _BIDI_REQUEST_CONTAINER
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winspool.h
apiname:
-	BIDI_REQUEST_CONTAINER
product: Windows
targetos: Windows
req.typenames: BIDI_REQUEST_CONTAINER, *LPBIDI_REQUEST_CONTAINER, *PBIDI_REQUEST_CONTAINER
req.product: Windows 10 or later.
---

# _BIDI_REQUEST_CONTAINER structure


## -description


The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests.


## -syntax


````
typedef struct _BIDI_REQUEST_CONTAINER {
  DWORD             Version;
  DWORD             Flags;
  DWORD             Count;
  BIDI_REQUEST_DATA aData[1];
} BIDI_REQUEST_CONTAINER, *PBIDI_REQUEST_CONTAINER, *LPBIDI_REQUEST_CONTAINER;
````


## -struct-fields




#### - Version

Specifies the version of the bidi API Schema, which is currently 1.


#### - Flags

Is a set of flags reserved for system use. This must be zero.


#### - Count

Specifies the number of bidi requests in the <b>aData</b> member. A container can contain zero or more requests, although a value of zero is valid only if the action is BIDI_ACTION_ENUM_SCHEMA.


#### - aData

Is an array of <a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a> structures, each holding a single bidi request. 


## -remarks


Even though the <b>aData</b> member of this structure is an array with only a single array element, <b>aData</b>[0] should be thought of as the first element of an array of (possibly) an arbitrarily large size. 



## -see-also

<a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_REQUEST_CONTAINER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

