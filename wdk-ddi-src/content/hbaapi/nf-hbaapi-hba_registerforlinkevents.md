---
UID: NF:hbaapi.HBA_RegisterForLinkEvents
title: HBA_RegisterForLinkEvents function
author: windows-driver-content
description: The HBA_RegisterForLinkEvents routine registers with a specified adapter for asynchronous fabric link-level events.
old-location: storage\hba_registerforlinkevents.htm
old-project: storage
ms.assetid: f0e6834c-b827-4342-83f1-5980f8edce24
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hba_registerforlinkevents, fibreHBA_rtns_7fd8f7c4-faaf-4190-99c8-560615e14365.xml, HBA_RegisterForLinkEvents routine [Storage Devices], hbaapi/HBA_RegisterForLinkEvents, HBA_RegisterForLinkEvents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_RegisterForLinkEvents
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RegisterForLinkEvents function


## -description


The <b>HBA_RegisterForLinkEvents</b> routine registers with a specified adapter for asynchronous fabric link-level events. 


## -syntax


````
HBA_STATUS HBA_API HBA_RegisterForLinkEvents(
   HBA_LINK_CALLBACK  callback,
   void               *userData,
   void               *pRLIRBuffer,
   HBA_UINT32         RLIRBufferSize,
   HBA_HANDLE         handle,
   HBA_CALLBACKHANDLE *callbackHandle
);
````


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556121">HBA_LINK_CALLBACK</a> to call when the event occurs. 


### -param userData

Pointer to user input data that is passed to the callback routine when it is called with each occurrence of the event. This data can synchronize the event handling with event registration.


### -param pRLIRBuffer

Pointer to registered link incident report (RLIR) data that is passed to the callback routine with each occurrence of the event. This data is overwritten by the callback routine each time it is called. 


### -param RLIRBufferSize

Contains the size, in bytes, of the buffer at <i>pRLIRBuffer</i>.


### -param Handle

TBD


### -param pCallbackHandle

TBD




#### - handle

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA for which event callbacks are requested.


#### - callbackHandle

Pointer to an opaque identifier that may be used to deregister the caller and suspend calls to the callback routine when events occur.


## -returns



The <b>HBA_RegisterForLinkEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RegisterForLinkEvents</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the callback registration was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if either the library or the system does not support events. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the registration of the callback routine. 

</td>
</tr>
</table>
 




## -remarks



Only RLIR events are reported. To stop event delivery, call <a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556121">HBA_LINK_CALLBACK</a>



<a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RegisterForLinkEvents routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

