---
UID: NF:d3dkmthk.D3DKMTDestroyProtectedSession
title: D3DKMTDestroyProtectedSession function
author: windows-driver-content
description: Used to destroy a protected session.
old-location: display\d3dkmtdestroyprotectedsession.htm
old-project: display
ms.assetid: e27ab1db-647d-447c-b79d-2553aa088398
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTDestroyProtectedSession, display.d3dkmtdestroyprotectedsession, D3DKMTDestroyProtectedSession method [Display Devices], D3DKMTDestroyProtectedSession
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
-	D3DKMTDestroyProtectedSession
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyProtectedSession function


## -description



			
            Used to destroy a protected session.


## -syntax


````
NTSTATUS  D3DKMTDestroyProtectedSession(
  _Inout_ D3DKMT_DESTROYPROTECTEDSESSION  *D3dkmt_destroyprotectedsession
);
````


## -parameters






#### - D3dkmt_destroyprotectedsession [in, out]

Holds information to destroy a protected session.


## -returns




Returns STATUS_SUCCESS if completed successfully.



