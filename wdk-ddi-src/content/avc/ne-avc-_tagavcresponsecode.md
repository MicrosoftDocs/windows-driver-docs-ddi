---
UID: NE:avc._tagAvcResponseCode
title: _tagAvcResponseCode
author: windows-driver-content
description: The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_SEND_RESPONSE function codes.
old-location: stream\avcresponsecode.htm
old-project: stream
ms.assetid: 81a0ff7f-60a0-437e-8db2-ac364000d580
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _tagAvcResponseCode, AvcResponseCode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AvcResponseCode
req.alt-loc: avc.h
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
req.typenames: AvcResponseCode
---

# _tagAvcResponseCode enumeration



## -description
The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through <b>AVC_FUNCTION_COMMAND</b> or <b>AVC_FUNCTION_SEND_RESPONSE</b> function codes.



## -syntax

````
typedef enum _tagAvcResponseCode { 
  AVC_RESPONSE_NOTIMPL        = 0x08,
  AVC_RESPONSE_ACCEPTED       = 0x09,
  AVC_RESPONSE_REJECTED       = 0x0a,
  AVC_RESPONSE_IN_TRANSITION  = 0x0b,
  AVC_RESPONSE_STABLE         = 0x0c,
  AVC_RESPONSE_IMPLEMENTED    = 0x0c,
  AVC_RESPONSE_CHANGED        = 0x0d,
  AVC_RESPONSE_INTERIM        = 0x0f
} AvcResponseCode;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554150">AVC_FUNCTION_COMMAND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554170">AVC_FUNCTION_SEND_RESPONSE</a>
</dt>
<dt>
<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AvcResponseCode enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

