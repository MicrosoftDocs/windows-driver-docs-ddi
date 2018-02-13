---
UID: NE:pointofservicedriverinterface._MsrTrackIds
title: "_MsrTrackIds"
author: windows-driver-content
description: Defines the constants that represent the magnetic stripe reader (MSR) tracks.
old-location: pos\msrtrackids.htm
old-project: pos
ms.assetid: 9366722a-c545-411d-a59f-63edfb0cd68e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pointofservicedriverinterface/MsrTrackIds_Track4, MsrTrackIds, pointofservicedriverinterface/MsrTrackIds_None, MsrTrackIds enumeration, pointofservicedriverinterface/MsrTrackIds_Track2, MsrTrackIds_None, pointofservicedriverinterface/MsrTrackIds_Track1, pointofservicedriverinterface/MsrTrackIds_Track3, pointofservicedriverinterface/MsrTrackIds, pos.msrtrackids, MsrTrackIds_Track4, MsrTrackIds_Track2, MsrTrackIds_Track1, MsrTrackIds_Track3, _MsrTrackIds
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
-	pointofservicedriverinterface.h
apiname:
-	MsrTrackIds
product: Windows
targetos: Windows
req.typenames: MsrTrackIds
---

# _MsrTrackIds enumeration


## -description


Defines the constants that represent the magnetic stripe reader (MSR) tracks.


## -syntax


````
typedef enum _MsrTrackIds { 
  MsrTrackIds_None    = 0x0,
  MsrTrackIds_Track1  = 0x1,
  MsrTrackIds_Track2  = 0x2,
  MsrTrackIds_Track3  = 0x3,
  MsrTrackIds_Track4  = 0x4
} MsrTrackIds;
````


## -enum-fields




### -field MsrTrackIds_None


### -field MsrTrackIds_Track1


### -field MsrTrackIds_Track2


### -field MsrTrackIds_Track3


### -field MsrTrackIds_Track4

