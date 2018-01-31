---
UID: NE:pointofservicedriverinterface._MsrStatisticsEntryType
title: "_MsrStatisticsEntryType"
author: windows-driver-content
description: This enumeration defines the kinds of magnetic stripe reader statistics.
old-location: pos\mststatisticsentrytype.htm
old-project: pos
ms.assetid: b3c9fac6-79b3-4a81-92af-004eb17a22f5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: MsrStatisticsEntryType_ParityLRCErrorTrack2Count, pointofservicedriverinterface/MsrStatisticsEntryType_ChallengeRequestCount, pointofservicedriverinterface/MsrStatisticsEntryType_GoodReadCount, pointofservicedriverinterface/MsrStatisticsEntryType_ParityLRCErrorTrack1Count, pointofservicedriverinterface/MsrStatisticsEntryType_GoodDeviceAuthenticationCount, pointofservicedriverinterface/MsrStatisticsEntryType_ParityLRCErrorTrack2Count, pointofservicedriverinterface/MsrStatisticsEntryType_Invalid, MsrStatisticsEntryType_HoursPoweredCount, MsrStatisticsEntryType_FailedCardAuthenticationDataCount, MsrStatisticsEntryType_ParityLRCErrorTrack4Count, MsrStatisticsEntryType_ParityLRCErrorTrack1Count, pointofservicedriverinterface/MsrStatisticsEntryType_ParityLRCErrorTrack3Count, MsrStatisticsEntryType_GoodDeviceAuthenticationCount, pointofservicedriverinterface/MsrStatisticsEntryType_FailedReadCount, pointofservicedriverinterface/MsrStatisticsEntryType_HoursPoweredCount, MsrStatisticsEntryType_FailedDeviceAuthenticationCount, pointofservicedriverinterface/MsrStatisticsEntryType_Count, MsrStatisticsEntryType_GoodCardAuthenticationDataCount, pointofservicedriverinterface/MsrStatisticsEntryType_FailedCardAuthenticationDataCount, MsrStatisticsEntryType_MissingStartSentinelTrack3Count, pointofservicedriverinterface/MstStatisticsEntryType, pointofservicedriverinterface/MsrStatisticsEntryType_FailedWriteCount, MsrStatisticsEntryType_MissingStartSentinelTrack1Count, MsrStatisticsEntryType_Count, pointofservicedriverinterface/MsrStatisticsEntryType_MissingStartSentinelTrack3Count, pointofservicedriverinterface/MsrStatisticsEntryType_MissingStartSentinelTrack2Count, MstStatisticsEntryType enumeration, MsrStatisticsEntryType_UnreadableCardCount, MsrStatisticsEntryType_Invalid, pointofservicedriverinterface/MsrStatisticsEntryType_ParityLRCErrorTrack4Count, MsrStatisticsEntryType_FailedWriteCount, pointofservicedriverinterface/MsrStatisticsEntryType_FailedDeviceAuthenticationCount, pointofservicedriverinterface/MsrStatisticsEntryType_UnreadableCardCount, pos.mststatisticsentrytype, pointofservicedriverinterface/MsrStatisticsEntryType_MissingStartSentinelTrack4Count, MsrStatisticsEntryType_GoodWriteCount, pointofservicedriverinterface/MsrStatisticsEntryType_MissingStartSentinelTrack1Count, MstStatisticsEntryType, MsrStatisticsEntryType_MissingStartSentinelTrack2Count, MsrStatisticsEntryType_MissingStartSentinelTrack4Count, MsrStatisticsEntryType_ChallengeRequestCount, _MsrStatisticsEntryType, MsrStatisticsEntryType_ParityLRCErrorTrack3Count, pointofservicedriverinterface/MsrStatisticsEntryType_CommunicationErrorCount, MsrStatisticsEntryType_FailedReadCount, MsrStatisticsEntryType_GoodReadCount, pointofservicedriverinterface/MsrStatisticsEntryType_GoodWriteCount, MsrStatisticsEntryType_CommunicationErrorCount, pointofservicedriverinterface/MsrStatisticsEntryType_GoodCardAuthenticationDataCount
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
-	MstStatisticsEntryType
product: Windows
targetos: Windows
req.typenames: MstStatisticsEntryType
---

# _MsrStatisticsEntryType enumeration


## -description


This enumeration defines the kinds of magnetic stripe reader statistics.


## -syntax


````
typedef enum _MstStatisticsEntryType { 
  MsrStatisticsEntryType_Invalid                            = -1,
  MsrStatisticsEntryType_HoursPoweredCount,
  MsrStatisticsEntryType_CommunicationErrorCount,
  MsrStatisticsEntryType_GoodReadCount,
  MsrStatisticsEntryType_FailedReadCount,
  MsrStatisticsEntryType_UnreadableCardCount,
  MsrStatisticsEntryType_GoodWriteCount,
  MsrStatisticsEntryType_FailedWriteCount,
  MsrStatisticsEntryType_MissingStartSentinelTrack1Count,
  MsrStatisticsEntryType_ParityLRCErrorTrack1Count,
  MsrStatisticsEntryType_MissingStartSentinelTrack2Count,
  MsrStatisticsEntryType_ParityLRCErrorTrack2Count,
  MsrStatisticsEntryType_MissingStartSentinelTrack3Count,
  MsrStatisticsEntryType_ParityLRCErrorTrack3Count,
  MsrStatisticsEntryType_MissingStartSentinelTrack4Count,
  MsrStatisticsEntryType_ParityLRCErrorTrack4Count,
  MsrStatisticsEntryType_GoodCardAuthenticationDataCount,
  MsrStatisticsEntryType_FailedCardAuthenticationDataCount,
  MsrStatisticsEntryType_ChallengeRequestCount,
  MsrStatisticsEntryType_GoodDeviceAuthenticationCount,
  MsrStatisticsEntryType_FailedDeviceAuthenticationCount,
  MsrStatisticsEntryType_Count
} MstStatisticsEntryType;
````


## -enum-fields




#### - MsrStatisticsEntryType_Invalid

Reserved for internal use.


#### - MsrStatisticsEntryType_HoursPoweredCount

Number of hours that the device has been powered on.


#### - MsrStatisticsEntryType_CommunicationErrorCount

Number of communication errors.


#### - MsrStatisticsEntryType_GoodReadCount

Number of successful reads



#### - MsrStatisticsEntryType_FailedReadCount

Number of failed reads



#### - MsrStatisticsEntryType_UnreadableCardCount

Number of unreadable cards



#### - MsrStatisticsEntryType_GoodWriteCount

Number of successful writes. Do not use.


#### - MsrStatisticsEntryType_FailedWriteCount

Number of failed writes. Do not use.


#### - MsrStatisticsEntryType_MissingStartSentinelTrack1Count

Number of missing start sentinel errors on track 1. May indicate an empty track.


#### - MsrStatisticsEntryType_ParityLRCErrorTrack1Count

Number of Parity or LRC errors on track 1



#### - MsrStatisticsEntryType_MissingStartSentinelTrack2Count

Number of missing start sentinel errors on track 2. May indicate an empty track.


#### - MsrStatisticsEntryType_ParityLRCErrorTrack2Count

Number of Parity or LRC errors on track 2



#### - MsrStatisticsEntryType_MissingStartSentinelTrack3Count

Number of missing start sentinel errors on track 3. May indicate an empty track.


#### - MsrStatisticsEntryType_ParityLRCErrorTrack3Count

Number of Parity or LRC errors on track 3



#### - MsrStatisticsEntryType_MissingStartSentinelTrack4Count

Number of missing start sentinel errors on track 4. May indicate an empty track.


#### - MsrStatisticsEntryType_ParityLRCErrorTrack4Count

Number of Parity or LRC errors on track 4



#### - MsrStatisticsEntryType_GoodCardAuthenticationDataCount

Number of successful card authentication data reads



#### - MsrStatisticsEntryType_FailedCardAuthenticationDataCount

Number of failed card authentication data reads



#### - MsrStatisticsEntryType_ChallengeRequestCount

Number of successful calls to <a href="https://msdn.microsoft.com/f94ce49d-ab87-4d8f-8fc7-af8899b37ca1">RetrieveDeviceAuthenticationDataAsync</a>.


#### - MsrStatisticsEntryType_GoodDeviceAuthenticationCount

Number of successful card authentication attempts



#### - MsrStatisticsEntryType_FailedDeviceAuthenticationCount

Number of failed card authentication attempts



#### - MsrStatisticsEntryType_Count

Count of entry types


