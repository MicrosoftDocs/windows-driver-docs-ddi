---
UID: NE:avc._tagAvcResponseCode
title: _tagAvcResponseCode (avc.h)
description: The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_SEND_RESPONSE function codes.
old-location: stream\avcresponsecode.htm
tech.root: stream
ms.assetid: 81a0ff7f-60a0-437e-8db2-ac364000d580
ms.date: 04/23/2018
keywords: ["tagAvcResponseCode enumeration"]
ms.keywords: AVC_RESPONSE_ACCEPTED, AVC_RESPONSE_CHANGED, AVC_RESPONSE_IMPLEMENTED, AVC_RESPONSE_INTERIM, AVC_RESPONSE_IN_TRANSITION, AVC_RESPONSE_NOTIMPL, AVC_RESPONSE_REJECTED, AVC_RESPONSE_STABLE, AvcResponseCode, AvcResponseCode enumeration [Streaming Media Devices], _tagAvcResponseCode, avc/AVC_RESPONSE_ACCEPTED, avc/AVC_RESPONSE_CHANGED, avc/AVC_RESPONSE_IMPLEMENTED, avc/AVC_RESPONSE_INTERIM, avc/AVC_RESPONSE_IN_TRANSITION, avc/AVC_RESPONSE_NOTIMPL, avc/AVC_RESPONSE_REJECTED, avc/AVC_RESPONSE_STABLE, avc/AvcResponseCode, avcref_28d2a6d6-4b1f-4b5e-af90-294da5dd14e5.xml, stream.avcresponsecode
req.header: avc.h
req.include-header: Avc.h
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
req.typenames: AvcResponseCode
f1_keywords:
 - _tagAvcResponseCode
 - avc/_tagAvcResponseCode
 - AvcResponseCode
 - avc/AvcResponseCode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - AvcResponseCode
---

# _tagAvcResponseCode enumeration


## -description

The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through <b>AVC_FUNCTION_COMMAND</b> or <b>AVC_FUNCTION_SEND_RESPONSE</b> function codes.

## -enum-fields

### -field AVC_RESPONSE_NOTIMPL

Indicates the subunit does not support the specified control command.

### -field AVC_RESPONSE_ACCEPTED

Indicates the subunit does implement the specified control command and that subunit state permits execution of the command. Note: Command execution may not have completed by the time the <b>AVC_RESPONSE_ACCEPTED</b> has been returned.

### -field AVC_RESPONSE_REJECTED

Specifies a response indicating the command or request was rejected.

### -field AVC_RESPONSE_IN_TRANSITION

Specifies a response indicating the command or request was accepted.

### -field AVC_RESPONSE_STABLE

Indicates the subunit implements the command. Same meaning as AVC_RESPONSE_IMPLMENTED.

### -field AVC_RESPONSE_IMPLEMENTED

Indicates the subunit implements the command. Same meaning as AVC_RESPONSE_STABLE.

### -field AVC_RESPONSE_CHANGED

Indicates the subunit state has changed.

### -field AVC_RESPONSE_INTERIM

Indicates the subunit is unable to respond with either <b>AVC_RESPONSE_ACCEPTED</b> or <b>AVC_RESPONSE_REJECTED</b> within the 100 millisecond timeframe for responses. The subunit will ultimately return a response frame with either a <b>AVC_RESPONSE_ACCEPTED</b> or <b>AVC_RESPONSE_REJECTED</b> code.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="/windows-hardware/drivers/stream/avc-function-command">AVC_FUNCTION_COMMAND</a>



<a href="/windows-hardware/drivers/stream/avc-function-send-response">AVC_FUNCTION_SEND_RESPONSE</a>