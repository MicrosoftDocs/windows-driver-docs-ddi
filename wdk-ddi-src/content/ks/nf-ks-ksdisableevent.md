---
UID: NF:ks.KsDisableEvent
title: KsDisableEvent function
author: windows-driver-content
description: The KsDisableEvent function disables events requested through IOCTL_KS_DISABLE_EVENT.
old-location: stream\ksdisableevent.htm
old-project: stream
ms.assetid: 4af94bc4-9df3-4b37-a810-303748cc4b75
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksfunc_e430d502-c847-43ee-bdea-d53200f45e53.xml, ks/KsDisableEvent, stream.ksdisableevent, KsDisableEvent, KsDisableEvent function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDisableEvent
product: Windows
targetos: Windows
req.typenames: 
---

# KsDisableEvent function


## -description


The <b>KsDisableEvent </b>function disables events requested through IOCTL_KS_DISABLE_EVENT. It responds to all events previously enabled through <b>KsEnableEvent</b>. If the input buffer length is zero, it is assumed that all events on the list are to be disabled. This function can only be called at PASSIVE_LEVEL.


## -syntax


````
NTSTATUS KsDisableEvent(
  _In_    PIRP              Irp,
  _Inout_ PLIST_ENTRY       EventsList,
  _In_    KSEVENTS_LOCKTYPE EventsFlags,
  _In_    PVOID             EventsLock
);
````


## -parameters




### -param Irp [in]

Specifies the IRP passed to the removal function, which uses the IRP to obtain context information. The file object associated with the IRP is used to compare against the file object originally specified when enabling the event. This allows a single event list to be used for multiple clients differentiated by file objects.


### -param EventsList [in, out]

Points to the head of the list of <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> items on which the event may be found. If a client uses multiple event lists and does not know what list this event is on, the client can call this function multiple times. An event not found will return STATUS_UNSUCCESSFUL.


### -param EventsFlags [in]

Specifies a <a href="..\ks\ne-ks-ksevents_locktype.md">KSEVENTS_LOCKTYPE</a> flag specifying the type of exclusion lock to be used in accessing the event list. If no flag is set, then no lock is taken.


### -param EventsLock [in]

Used to synchronize access to an element on the list. After the element has been accessed, it is marked as being deleted so that subsequent removal requests fail. The lock is then released after calling the removal function, if any. The removal function must synchronize with event generation before actually removing the element from the list.


## -returns



The <b>KsDisableEvent </b>function returns STATUS_SUCCESS if successful, or an error specific to the event being enabled. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero. It does not set the IO_STATUS_BLOCK.Status field, nor does it complete the IRP.




## -remarks



It is important that the remove handler synchronize with event generation to ensure that when the event is removed from the list, it is not currently being serviced. Access to this list is assumed to be controlled with the lock passed. 




## -see-also

<a href="..\ks\nf-ks-ksenableevent.md">KsEnableEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDisableEvent function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

