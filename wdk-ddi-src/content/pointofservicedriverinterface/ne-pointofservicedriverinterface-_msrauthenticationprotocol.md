---
UID: NE:pointofservicedriverinterface._MsrAuthenticationProtocol
title: _MsrAuthenticationProtocol (pointofservicedriverinterface.h)
description: This enumeration defines magnetic stripe reader (MSR) authentication protocols.
old-location: pos\msrauthenticationprotocoltype.htm
tech.root: pos
ms.assetid: 6f06d03e-001e-4340-9b96-8e3654be5c1a
ms.date: 02/23/2018
keywords: ["_MsrAuthenticationProtocol enumeration"]
ms.keywords: MsrAuthenticationProtocol, MsrAuthenticationProtocol enumeration, MsrAuthenticationProtocolType, MsrAuthenticationProtocolType enumeration, MsrAuthenticationProtocolType_ChallengeResponse, MsrAuthenticationProtocolType_None, _MsrAuthenticationProtocol, pointofservicedriverinterface/MsrAuthenticationProtocolType, pointofservicedriverinterface/MsrAuthenticationProtocolType_ChallengeResponse, pointofservicedriverinterface/MsrAuthenticationProtocolType_None, pos.msrauthenticationprotocoltype
f1_keywords:
 - "pointofservicedriverinterface/MsrAuthenticationProtocol"
 - "MsrAuthenticationProtocol"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pointofservicedriverinterface.h
api_name:
- MsrAuthenticationProtocol
product:
- Windows
targetos: Windows
req.typenames: MsrAuthenticationProtocolType
---

# _MsrAuthenticationProtocol enumeration


## -description


This enumeration defines magnetic stripe reader (MSR) authentication protocols.


## -enum-fields




### -field MsrAuthenticationProtocolType_None

Authentication is not supported.


### -field MsrAuthenticationProtocolType_ChallengeResponse

Challenge-response authentication is supported.


## -remarks



<div class="alert"><b>Tip</b>  Password authentication is an example of challenge-response authentication.</div>
<div> </div>


