---
UID: NE:ks.KSEVENT_CONNECTION
title: KSEVENT_CONNECTION
author: windows-driver-content
description: "."
old-location: stream\ksevent_connection.htm
old-project: stream
ms.assetid: E85946B3-90B6-41CA-9F69-47B33AE8D851
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSEVENT_CONNECTION enumeration [Streaming Media Devices], KSEVENT_CONNECTION_POSITIONUPDATE, ks/KSEVENT_CONNECTION_TIMEDISCONTINUITY, ks/KSEVENT_CONNECTION_PRIORITY, KSEVENT_CONNECTION_PRIORITY, ks/KSEVENT_CONNECTION_ENDOFSTREAM, ks/KSEVENT_CONNECTION_DATADISCONTINUITY, ks/KSEVENT_CONNECTION_POSITIONUPDATE, KSEVENT_CONNECTION_TIMEDISCONTINUITY, KSEVENT_CONNECTION_ENDOFSTREAM, KSEVENT_CONNECTION_DATADISCONTINUITY, KSEVENT_CONNECTION, ks/KSEVENT_CONNECTION, stream.ksevent_connection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: 
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
-	Ks.h
apiname:
-	KSEVENT_CONNECTION
product: Windows
targetos: Windows
req.typenames: KSEVENT_CONNECTION
---

# KSEVENT_CONNECTION enumeration


## -description





## -syntax


````
typedef enum  { 
  KSEVENT_CONNECTION_POSITIONUPDATE,
  KSEVENT_CONNECTION_DATADISCONTINUITY,
  KSEVENT_CONNECTION_TIMEDISCONTINUITY,
  KSEVENT_CONNECTION_PRIORITY,
  KSEVENT_CONNECTION_ENDOFSTREAM
} KSEVENT_CONNECTION;
````


## -enum-fields




### -field KSEVENT_CONNECTION_POSITIONUPDATE



### -field KSEVENT_CONNECTION_DATADISCONTINUITY



### -field KSEVENT_CONNECTION_TIMEDISCONTINUITY



### -field KSEVENT_CONNECTION_PRIORITY



### -field KSEVENT_CONNECTION_ENDOFSTREAM


