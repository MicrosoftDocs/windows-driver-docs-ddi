---
UID: NE:avc._tagAvcCommandType
title: "_tagAvcCommandType"
author: windows-driver-content
description: The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_GET_REQUEST function codes.
old-location: stream\avccommandtype.htm
old-project: stream
ms.assetid: 18bf43bd-3499-4494-839b-9bc07de83644
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVC_CTYPE_CONTROL, AVC_CTYPE_GEN_INQ, AVC_CTYPE_NOTIFY, AVC_CTYPE_SPEC_INQ, AVC_CTYPE_STATUS, AvcCommandType, AvcCommandType enumeration [Streaming Media Devices], _tagAvcCommandType, avc/AVC_CTYPE_CONTROL, avc/AVC_CTYPE_GEN_INQ, avc/AVC_CTYPE_NOTIFY, avc/AVC_CTYPE_SPEC_INQ, avc/AVC_CTYPE_STATUS, avc/AvcCommandType, avcref_08c9f0bb-efe0-412d-9a49-ba497bcc6e25.xml, stream.avccommandtype
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	avc.h
api_name:
-	AvcCommandType
product: Windows
targetos: Windows
req.typenames: AvcCommandType
---

# _tagAvcCommandType enumeration


## -description


The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through <b>AVC_FUNCTION_COMMAND</b> or <b>AVC_FUNCTION_GET_REQUEST</b> function codes.


## -syntax


````
typedef enum _tagAvcCommandType { 
  AVC_CTYPE_CONTROL   = 0x00,
  AVC_CTYPE_STATUS    = 0x01,
  AVC_CTYPE_SPEC_INQ  = 0x02,
  AVC_CTYPE_NOTIFY    = 0x03,
  AVC_CTYPE_GEN_INQ   = 0x04
} AvcCommandType;
````


## -enum-fields




### -field AVC_CTYPE_CONTROL

Specifies a control type of command.


### -field AVC_CTYPE_STATUS

Specifies a status type of command.


### -field AVC_CTYPE_SPEC_INQ

Specifies a specific-inquiry type of command. This permits a controller to inform targets that a specific set of operands must by furnished along with the opcode when issuing a command.


### -field AVC_CTYPE_NOTIFY

Specifies a notify type of command.


### -field AVC_CTYPE_GEN_INQ

Specifies a general inquiry command type. This permits a controller to query a target to find out if it supports a specific opcode without needing to pass any specific operands.


## -see-also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554163">AVC_FUNCTION_GET_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554150">AVC_FUNCTION_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AvcCommandType enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

