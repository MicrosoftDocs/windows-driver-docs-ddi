---
UID: NF:hbaapi.HBA_RegisterForAdapterAddEvents
title: HBA_RegisterForAdapterAddEvents function
author: windows-driver-content
description: The HBA_RegisterForAdapterAddEvents routine registers the indicated user callback routine to call when a new adapter is added to the system.
old-location: storage\hba_registerforadapteraddevents.htm
old-project: storage
ms.assetid: 7395ccb8-2608-46ae-a378-987bd757761b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_RegisterForAdapterAddEvents
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
req.alt-api: HBA_RegisterForAdapterAddEvents
req.alt-loc: Hbaapi.dll
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
req.typenames: HBA_WWNTYPE
---

# HBA_RegisterForAdapterAddEvents function



## -description
The <b>HBA_RegisterForAdapterAddEvents</b> routine registers the indicated user callback routine to call when a new adapter is added to the system. 



## -syntax

````
HBA_STATUS HBA_API HBA_RegisterForAdapterAddEvents(
  _In_ void       callback,
       HBA_WWN    userData,
       HBA_UINT32 callbackHandle
);
````


## -parameters

### -param callback [in]

Pointer to a callback routine of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a> that is called when an adapter is added to the system.


### -param userData 

Pointer to a buffer that will be passed to the callback routine with each event. This data correlates the event with the source of the event registration. 


### -param callbackHandle 

Contains an opaque identifier that the user must pass to <a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a> to de-register the callback routine.


## -returns
The <b>HBA_RegisterForAdapterAddEvents</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, this member should have one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the callback routine was successfully registered. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the registration of the callback routine. 

 


## -remarks
When a new adapter is added to the system, an event of type HBA_EVENT_ADAPTER_ADD is generated.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556045">HBA_ADAPTER_CALLBACK</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_removecallback.md">HBA_RemoveCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RegisterForAdapterAddEvents routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

