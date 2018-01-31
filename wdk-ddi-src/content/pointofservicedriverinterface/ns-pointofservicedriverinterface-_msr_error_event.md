---
UID: NS:pointofservicedriverinterface._MSR_ERROR_EVENT
title: "_MSR_ERROR_EVENT"
author: windows-driver-content
description: This structure contains the error data that is passed to the MagneticStripeReaderErrorOccured event.
old-location: pos\msr_error_event.htm
old-project: pos
ms.assetid: daab2df5-4d23-4fe3-b357-74b2615e6d1e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pointofservicedriverinterface/MSR_ERROR_EVENT, *PMSR_ERROR_EVENT, _MSR_ERROR_EVENT, PMSR_ERROR_EVENT, pointofservicedriverinterface/PMSR_ERROR_EVENT, MSR_ERROR_EVENT structure, MSR_ERROR_EVENT, PMSR_ERROR_EVENT structure pointer, pos.msr_error_event
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	MSR_ERROR_EVENT
product: Windows
targetos: Windows
req.typenames: "*PMSR_ERROR_EVENT, MSR_ERROR_EVENT"
---

# _MSR_ERROR_EVENT structure


## -description


This structure contains the error data that is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772151">MagneticStripeReaderErrorOccured</a> event.


## -syntax


````
typedef struct _MSR_ERROR_EVENT {
  PosEventDataHeader      Header;
  MsrTrackErrorType       Track1Status;
  MsrTrackErrorType       Track2Status;
  MsrTrackErrorType       Track3Status;
  MsrTrackErrorType       Track4Status;
  UnifiedPosErrorSeverity Severity;
  UnifiedPosErrorReason   Reason;
  UINT32                  ExtendedReason;
  MSR_DATA_RECEIVED       CardData;
  wchar_t                 Message[MSR_ERROR_MAX_MESSAGE_LENGTH];
} MSR_ERROR_EVENT, *PMSR_ERROR_EVENT;
````


## -struct-fields




#### - Header

Track 4 error status.


#### - Track1Status

Track 1 error status.


#### - Track2Status

Track 2 error status.


#### - Track3Status

Track 3 error status.


#### - Track4Status

Track 4 error status.


#### - Severity

Severity of the error.


#### - Reason

Reason for the error.


#### - ExtendedReason

Additional information about the error.


#### - CardData

Data read from a swiped magnetic stripe card.


#### - Message

NULL terminated error message.

