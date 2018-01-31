---
UID: NF:d3dkmthk.D3DKMTCreateProtectedSession
title: D3DKMTCreateProtectedSession function
author: windows-driver-content
description: Used to create a protected session.
old-location: display\d3dkmtcreateprotectedsession.htm
old-project: display
ms.assetid: f6967f07-564b-4730-9950-4703b541165b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTCreateProtectedSession, D3DKMTCreateProtectedSession, D3DKMTCreateProtectedSession method [Display Devices], display.d3dkmtcreateprotectedsession
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMTCreateProtectedSession
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateProtectedSession function


## -description



			
            Used to create a protected session.


## -syntax


````
NTSTATUS  D3DKMTCreateProtectedSession(
  _Inout_ D3DKMT_CREATEPROTECTEDSESSION  D3dkmt_createprotectedsession
);
````


## -parameters





#### - D3dkmt_createprotectedsession [in, out]

Holds information to create a protected session.


## -returns



Returns STATUS_SUCCESS if completed successfully.


