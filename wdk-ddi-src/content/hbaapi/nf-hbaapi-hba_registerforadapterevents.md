---
UID: NF:hbaapi.HBA_RegisterForAdapterEvents
title: HBA_RegisterForAdapterEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterEvents routine registers the indicated user callback routine to call when an adapter event occurs.
old-location: storage\hba_registerforadapterevents.htm
old-project: storage
ms.assetid: b5e671dc-0583-4e5f-b537-3257b3f25479
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_RegisterForAdapterEvents routine [Storage Devices], HBA_RegisterForAdapterEvents, hbaapi/HBA_RegisterForAdapterEvents, storage.hba_registerforadapterevents, fibreHBA_rtns_8ab64c5b-ffac-4e2a-90db-5f3cbc640f14.xml
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
-	HBA_RegisterForAdapterEvents
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RegisterForAdapterEvents function


## -description


The <b>HBA_RegisterForAdapterEvents</b> routine registers the indicated user callback routine to call when an adapter event occurs. 


## -syntax


````
HBA_STATUS HBA_API HBA_RegisterForAdapterEvents(
   HBA_ADAPTER_CALLBACK callback,
   void                 *userData,
   HBA_HANDLE           handle,
   HBA_CALLBACKHANDLE   *callbackHandle
);
````


## -parameters




### -param callback

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a> that is called when an adapter is added to the system.


### -param pUserData

TBD


### -param Handle

TBD


### -param pCallbackHandle

TBD



#### - userData

Pointer to a buffer that is passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


#### - handle

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA for which the adapter events are generated. 


#### - callbackHandle

Contains an opaque identifier that the user must pass to <a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a> to de-register the callback routine.


## -returns


The <b>HBA_RegisterForAdapterEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.
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
Returned if the callback routine was successfully registered. 

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


If the HBA referenced by <i>handle </i>is removed from the system, the callback function is called with event type of HBA_EVENT_ADAPTER_REMOVE.

If the configuration of the HBA referenced by <i>handle </i>is changed, the callback function is called with event type of HBA_EVENT_ADAPTER_CHANGE.



## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RegisterForAdapterEvents routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

