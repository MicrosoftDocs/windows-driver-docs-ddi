---
UID: NS:pointofservicedriverinterface._MSR_ERROR_EVENT
title: _MSR_ERROR_EVENT (pointofservicedriverinterface.h)
description: This structure contains the error data that is passed to the MagneticStripeReaderErrorOccured event.
old-location: pos\msr_error_event.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["MSR_ERROR_EVENT structure"]
ms.keywords: "*PMSR_ERROR_EVENT, MSR_ERROR_EVENT, MSR_ERROR_EVENT structure, PMSR_ERROR_EVENT, PMSR_ERROR_EVENT structure pointer, _MSR_ERROR_EVENT, pointofservicedriverinterface/MSR_ERROR_EVENT, pointofservicedriverinterface/PMSR_ERROR_EVENT, pos.msr_error_event"
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
targetos: Windows
req.typenames: MSR_ERROR_EVENT, *PMSR_ERROR_EVENT
f1_keywords:
 - _MSR_ERROR_EVENT
 - pointofservicedriverinterface/_MSR_ERROR_EVENT
 - PMSR_ERROR_EVENT
 - pointofservicedriverinterface/PMSR_ERROR_EVENT
 - MSR_ERROR_EVENT
 - pointofservicedriverinterface/MSR_ERROR_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - MSR_ERROR_EVENT
---

# _MSR_ERROR_EVENT structure


## -description

This structure contains the error data that is passed to the <a href="/previous-versions/windows/hardware/previsioning-framework/dn772151(v=vs.85)">MagneticStripeReaderErrorOccured</a> event.

## -struct-fields

### -field Header

Track 4 error status.

### -field Track1Status

Track 1 error status.

### -field Track2Status

Track 2 error status.

### -field Track3Status

Track 3 error status.

### -field Track4Status

Track 4 error status.

### -field Severity

Severity of the error.

### -field Reason

Reason for the error.

### -field ExtendedReason

Additional information about the error.

### -field CardData

Data read from a swiped magnetic stripe card.

### -field Message

NULL terminated error message.
