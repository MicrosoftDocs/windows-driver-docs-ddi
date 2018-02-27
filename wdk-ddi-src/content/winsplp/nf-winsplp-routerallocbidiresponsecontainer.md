---
UID: NF:winsplp.RouterAllocBidiResponseContainer
title: RouterAllocBidiResponseContainer function
author: windows-driver-content
description: RouterAllocBidiResponseContainer allocates a BIDI_RESPONSE_CONTAINER structure containing a list of bidi responses. The bidi response list is an array of BIDI_RESPONSE_DATA structures.
old-location: print\routerallocbidiresponsecontainer.htm
old-project: print
ms.assetid: ca10f0d5-62d6-451a-96e5-38aca18cf5b0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: RouterAllocBidiResponseContainer, RouterAllocBidiResponseContainer function [Print Devices], print.routerallocbidiresponsecontainer, spoolfnc_05ba5d83-8913-4591-9ada-2e57440354b9.xml, winsplp/RouterAllocBidiResponseContainer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Spoolss.dll
apiname:
-	RouterAllocBidiResponseContainer
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# RouterAllocBidiResponseContainer function


## -description


<code>RouterAllocBidiResponseContainer</code> allocates a <a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a> structure containing a list of bidi responses. The bidi response list is an array of <a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a> structures.


## -syntax


````
PBIDI_RESPONSE_CONTAINER RouterAllocBidiResponseContainer(
  _In_ DWORD cSize
);
````


## -parameters




### -param Count

TBD




#### - cSize [in]

Specifies the number of BIDI_RESPONSE_DATA structures to be allocated.


## -returns



<code>RouterAllocBidiResponseContainer</code> returns a pointer to the allocated structure, on success. If the function fails to allocate the structure, the caller can obtain the error code from <b>GetLastError</b> (described in the Microsoft Windows SDK documentation).




## -remarks



When the memory allocated by this function is no longer needed, use <a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>.




## -see-also

<a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a>



<a href="..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md">RouterFreeBidiResponseContainer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562071">SendRecvBidiDataFromPort</a>



<a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RouterAllocBidiResponseContainer function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

