---
UID: NC:61883.PBUS_RESET_ROUTINE
title: PBUS_RESET_ROUTINE (61883.h)
description: This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.
old-location: ieee\pbus_reset_routine.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["PBUS_RESET_ROUTINE callback function"]
ms.keywords: 61883/BusResetRoutine, BusResetRoutine, BusResetRoutine callback function [Buses], IEEE.pbus_reset_routine, PBUS_RESET_ROUTINE, PBUS_RESET_ROUTINE callback
req.header: 61883.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PBUS_RESET_ROUTINE
 - 61883/PBUS_RESET_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 61883.h
api_name:
 - BusResetRoutine
---

# PBUS_RESET_ROUTINE callback function


## -description

This is a caller-supplied function to be called by the protocol driver when the 1394 bus is reset.

## -parameters

### -param Context 

[in]
Pointer to the context supplied by the caller at the <b>Context</b> member of the input BUS_RESET_NOTIFY structure.

### -param BusResetInfo 

[in]
The bus reset information.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
