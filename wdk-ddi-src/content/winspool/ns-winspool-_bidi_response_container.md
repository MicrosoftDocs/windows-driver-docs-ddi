---
UID: NS:winspool._BIDI_RESPONSE_CONTAINER
title: "_BIDI_RESPONSE_CONTAINER"
author: windows-driver-content
description: The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses.
old-location: print\bidi_response_container.htm
old-project: print
ms.assetid: 26924dd2-ac67-408c-87e0-5cfb3281fe75
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*LPBIDI_RESPONSE_CONTAINER, *PBIDI_RESPONSE_CONTAINER, BIDI_RESPONSE_CONTAINER, BIDI_RESPONSE_CONTAINER structure [Print Devices], LPBIDI_RESPONSE_CONTAINER, LPBIDI_RESPONSE_CONTAINER structure pointer [Print Devices], PBIDI_RESPONSE_CONTAINER, PBIDI_RESPONSE_CONTAINER structure pointer [Print Devices], _BIDI_RESPONSE_CONTAINER, print.bidi_response_container, spoolfnc_79e5354d-1fc1-4156-8be9-028ebcd14b16.xml, winspool/BIDI_RESPONSE_CONTAINER, winspool/LPBIDI_RESPONSE_CONTAINER, winspool/PBIDI_RESPONSE_CONTAINER"
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
-	BIDI_RESPONSE_CONTAINER
product: Windows
targetos: Windows
req.typenames: BIDI_RESPONSE_CONTAINER, *PBIDI_RESPONSE_CONTAINER, *LPBIDI_RESPONSE_CONTAINER
req.product: Windows 10 or later.
---

# _BIDI_RESPONSE_CONTAINER structure


## -description


The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses.


## -syntax


````
typedef struct _BIDI_RESPONSE_CONTAINER {
  DWORD              Version;
  DWORD              Flags;
  DWORD              Count;
  BIDI_RESPONSE_DATA aData[1];
} BIDI_RESPONSE_CONTAINER, *PBIDI_RESPONSE_CONTAINER, *LPBIDI_RESPONSE_CONTAINER;
````


## -struct-fields




### -field Version

Specifies the version of the bidi API Schema, which is currently 1.


### -field Flags

Is a set of flags reserved for system use. This must be zero.


### -field Count

Specifies the number of responses in the <b>aData</b> member.


### -field aData

Is an array of <a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a> structures, each containing a single bidi response.


## -remarks



Even though the <b>aData</b> member of this structure is an array with only a single array element, <b>aData</b>[0] should be thought of as the first element of an array of (possibly) an arbitrarily large size.

The spooler's <a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a> function allocates the memory needed for this structure, which is then used to hold an array of BIDI_RESPONSE_DATA structures. When a BIDI_RESPONSE_CONTAINER structure is no longer needed, it should be freed by a call to <a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>.




## -see-also

<a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a>



<a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>



<a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20BIDI_RESPONSE_CONTAINER structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

