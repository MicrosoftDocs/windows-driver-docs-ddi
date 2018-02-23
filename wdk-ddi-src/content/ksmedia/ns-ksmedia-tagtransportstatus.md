---
UID: NS:ksmedia.tagTRANSPORTSTATUS
title: tagTRANSPORTSTATUS
author: windows-driver-content
description: The TRANSPORTSTATUS structure describes the current transport status.
old-location: stream\transportstatus.htm
old-project: stream
ms.assetid: 2896fd39-5c33-4c79-8adb-f6862b7b4314
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: tagTRANSPORTSTATUS, *PTRANSPORTSTATUS, TRANSPORTSTATUS, stream.transportstatus, TRANSPORTSTATUS structure [Streaming Media Devices], ksmedia/TRANSPORTSTATUS, PTRANSPORTSTATUS structure pointer [Streaming Media Devices], vidcapstruct_12a98ac2-58b9-47ce-ae09-30c8feeec2f0.xml, ksmedia/PTRANSPORTSTATUS, PTRANSPORTSTATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname:
-	TRANSPORTSTATUS
product: Windows
targetos: Windows
req.typenames: TRANSPORTSTATUS, *PTRANSPORTSTATUS
---

# tagTRANSPORTSTATUS structure


## -description


The TRANSPORTSTATUS structure describes the current transport status.


## -syntax


````
typedef struct tagTRANSPORTSTATUS {
  LONG Mode;
  LONG LastError;
  LONG RecordInhibit;
  LONG ServoLock;
  LONG MediaPresent;
  LONG MediaLength;
  LONG MediaSize;
  LONG MediaTrackCount;
  LONG MediaTrackLength;
  LONG MediaTrackSide;
  LONG MediaType;
  LONG LinkMode;
  LONG NotifyOn;
} TRANSPORTSTATUS, *PTRANSPORTSTATUS;
````


## -struct-fields




### -field Mode

Specifies the ED_MODE_Xxx.


### -field LastError

Specifies the last error.


### -field RecordInhibit

Specifies if recording is inhibited. <b>TRUE</b> if recording is prevented, <b>FALSE</b> otherwise.


### -field ServoLock

Indicates the servo lock.


### -field MediaPresent

Specifies if media is present.


### -field MediaLength

Specifies the length of the media.


### -field MediaSize

Specifies the size of the media.


### -field MediaTrackCount

Indicates the media track count.


### -field MediaTrackLength

Specifies the media track length.


### -field MediaTrackSide

Indicates the media track size.


### -field MediaType

Indicates the type of media.


### -field LinkMode

Indicates linked mode. <b>TRUE</b> if linked, <b>FALSE</b> otherwise.


### -field NotifyOn

Specifies event notification. <b>TRUE</b> enables event notification, <b>FALSE</b> disables event notification.


## -remarks



Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.



