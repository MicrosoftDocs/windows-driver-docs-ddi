---
UID: NF:winsplp.RouterFreeBidiResponseContainer
title: RouterFreeBidiResponseContainer function
author: windows-driver-content
description: RouterFreeBidiResponseContainer frees a BIDI_RESPONSE_CONTAINER structure previously allocated by RouterAllocBidiResponseContainer.
old-location: print\routerfreebidiresponsecontainer.htm
old-project: print
ms.assetid: 3998eed5-398e-4835-b917-54f5ae814ddf
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: spoolfnc_065c8a3a-5790-45f5-bf79-3af94fdd0571.xml, winsplp/RouterFreeBidiResponseContainer, RouterFreeBidiResponseContainer, RouterFreeBidiResponseContainer function [Print Devices], print.routerfreebidiresponsecontainer
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
req.lib: WinSpool.lib
req.dll: WinSpool.drv
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WinSpool.drv
apiname:
-	RouterFreeBidiResponseContainer
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# RouterFreeBidiResponseContainer function


## -description


<code>RouterFreeBidiResponseContainer</code> frees a <a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a> structure previously allocated by <a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a>.


## -syntax


````
DWORD RouterFreeBidiResponseContainer(
  _In_ PBIDI_RESPONSE_CONTAINER pData
);
````


## -parameters




### -param pData [in]

Pointer to the BIDI_RESPONSE_CONTAINER structure to be freed.


## -returns



<code>RouterFreeBidiResponseContainer</code> normally returns ERROR_SUCCESS, unless it throws an exception. In that case it returns an appropriate error code.




## -see-also

<a href="..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md">RouterAllocBidiResponseContainer</a>



<a href="..\winspool\ns-winspool-_bidi_response_container.md">BIDI_RESPONSE_CONTAINER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RouterFreeBidiResponseContainer function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

