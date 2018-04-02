---
UID: NE:pointofservicedriverinterface._MsrTrackErrorType
title: "_MsrTrackErrorType"
author: windows-driver-content
description: This enumeration defines the kinds of magnetic stripe reader track errors.
old-location: pos\msrtrackerrortype.htm
old-project: pos
ms.assetid: 2abd9341-527f-43af-baa2-622b759b47cd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: MsrTrackErrorType, MsrTrackErrorType enumeration, MsrTrackErrorType_EndSentinelError, MsrTrackErrorType_LrcError, MsrTrackErrorType_None, MsrTrackErrorType_ParityError, MsrTrackErrorType_StartSentinelError, MsrTrackErrorType_Unknown, _MsrTrackErrorType, pointofservicedriverinterface/MsrTrackErrorType, pointofservicedriverinterface/MsrTrackErrorType_EndSentinelError, pointofservicedriverinterface/MsrTrackErrorType_LrcError, pointofservicedriverinterface/MsrTrackErrorType_None, pointofservicedriverinterface/MsrTrackErrorType_ParityError, pointofservicedriverinterface/MsrTrackErrorType_StartSentinelError, pointofservicedriverinterface/MsrTrackErrorType_Unknown, pos.msrtrackerrortype
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicedriverinterface.h
api_name:
-	MsrTrackErrorType
product:
- Windows
targetos: Windows
req.typenames: MsrTrackErrorType
---

# _MsrTrackErrorType enumeration


## -description


This enumeration defines the kinds of magnetic stripe reader track errors.


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

