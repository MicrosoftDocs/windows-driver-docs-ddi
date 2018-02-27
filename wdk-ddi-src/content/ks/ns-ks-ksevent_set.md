---
UID: NS:ks.KSEVENT_SET
title: KSEVENT_SET
author: windows-driver-content
description: The KSEVENT_SET structure describes the events that comprise a kernel streaming event set.
old-location: stream\ksevent_set.htm
old-project: stream
ms.assetid: 0cfe3674-2261-44f5-a916-fb786bb25fe5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSEVENT_SET, KSEVENT_SET, KSEVENT_SET structure [Streaming Media Devices], PKSEVENT_SET, PKSEVENT_SET structure pointer [Streaming Media Devices], ks-struct_f3a678ec-93b4-4b60-959a-ca750b4ac4c2.xml, ks/KSEVENT_SET, ks/PKSEVENT_SET, stream.ksevent_set"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSEVENT_SET
product: Windows
targetos: Windows
req.typenames: KSEVENT_SET, *PKSEVENT_SET
---

# KSEVENT_SET structure


## -description


The KSEVENT_SET structure describes the events that comprise a kernel streaming event set.


## -syntax


````
typedef struct {
  const GUID         *Set;
  ULONG              EventsCount;
  const KSEVENT_ITEM *EventItem;
} KSEVENT_SET, *PKSEVENT_SET;
````


## -struct-fields




### -field Set

Specifies a GUID that identifies the event set. For more information about defined event sets, see <b>Remarks</b>.


### -field EventsCount

Specifies the number of events in the event set.


### -field EventItem

Points to the beginning of the array of <a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a> structures that describe each event in the event set. The size of the array is in the <b>EventsCount</b> member.


## -remarks



Microsoft provides several system-defined kernel streaming event set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming event sets typically begin with a <i>KSEVENTSETID</i> prefix. Event set GUIDs are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.




## -see-also

<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENT_SET structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

