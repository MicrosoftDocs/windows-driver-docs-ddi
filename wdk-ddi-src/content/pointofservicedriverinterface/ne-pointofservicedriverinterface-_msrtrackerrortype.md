---
UID: NE:pointofservicedriverinterface._MsrTrackErrorType
title: "_MsrTrackErrorType"
author: windows-driver-content
description: This enumeration defines the kinds of magnetic stripe reader track errors.
old-location: pos\msrtrackerrortype.htm
old-project: pos
ms.assetid: 2abd9341-527f-43af-baa2-622b759b47cd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: MsrTrackErrorType_StartSentinelError, pos.msrtrackerrortype, pointofservicedriverinterface/MsrTrackErrorType, pointofservicedriverinterface/MsrTrackErrorType_Unknown, MsrTrackErrorType_LrcError, pointofservicedriverinterface/MsrTrackErrorType_LrcError, MsrTrackErrorType, pointofservicedriverinterface/MsrTrackErrorType_StartSentinelError, _MsrTrackErrorType, MsrTrackErrorType_None, pointofservicedriverinterface/MsrTrackErrorType_EndSentinelError, pointofservicedriverinterface/MsrTrackErrorType_None, MsrTrackErrorType_ParityError, MsrTrackErrorType_Unknown, pointofservicedriverinterface/MsrTrackErrorType_ParityError, MsrTrackErrorType_EndSentinelError, MsrTrackErrorType enumeration
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	MsrTrackErrorType
product: Windows
targetos: Windows
req.typenames: MsrTrackErrorType
---

# _MsrTrackErrorType enumeration


## -description


This enumeration defines the kinds of magnetic stripe reader track errors.


## -syntax


````
typedef enum _MsrTrackErrorType { 
  MsrTrackErrorType_Unknown             = -1,
  MsrTrackErrorType_None                = 0,
  MsrTrackErrorType_StartSentinelError  = 1,
  MsrTrackErrorType_EndSentinelError    = 2,
  MsrTrackErrorType_ParityError         = 3,
  MsrTrackErrorType_LrcError            = 4
} MsrTrackErrorType;
````


## -enum-fields




### -field MsrTrackErrorType_Unknown

An unspecified error.


### -field MsrTrackErrorType_None

No error occurred.


### -field MsrTrackErrorType_StartSentinelError

A start sentinel error.


### -field MsrTrackErrorType_EndSentinelError

An end sentinel error.


### -field MsrTrackErrorType_ParityError

A parity error.


### -field MsrTrackErrorType_LrcError

A Longitudinal Redundancy Check (LRC) or checksum error.

