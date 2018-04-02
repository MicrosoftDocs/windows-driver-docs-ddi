---
UID: NE:pointofservicedriverinterface._MsrAuthenticationProtocol
title: "_MsrAuthenticationProtocol"
author: windows-driver-content
description: This enumeration defines magnetic stripe reader (MSR) authentication protocols.
old-location: pos\msrauthenticationprotocoltype.htm
old-project: pos
ms.assetid: 6f06d03e-001e-4340-9b96-8e3654be5c1a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: MsrAuthenticationProtocol, MsrAuthenticationProtocol enumeration, MsrAuthenticationProtocolType, MsrAuthenticationProtocolType enumeration, MsrAuthenticationProtocolType_ChallengeResponse, MsrAuthenticationProtocolType_None, _MsrAuthenticationProtocol, pointofservicedriverinterface/MsrAuthenticationProtocolType, pointofservicedriverinterface/MsrAuthenticationProtocolType_ChallengeResponse, pointofservicedriverinterface/MsrAuthenticationProtocolType_None, pos.msrauthenticationprotocoltype
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
-	MsrAuthenticationProtocol
product: Windows
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


