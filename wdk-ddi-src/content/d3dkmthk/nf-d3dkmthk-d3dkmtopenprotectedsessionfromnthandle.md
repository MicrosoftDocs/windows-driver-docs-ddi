---
UID: NF:d3dkmthk.D3DKMTOpenProtectedSessionFromNtHandle
title: D3DKMTOpenProtectedSessionFromNtHandle function
author: windows-driver-content
description: Used to open a protected session from the NT handle.
old-location: display\d3dkmtopenprotectedsessionfromnthandle.htm
old-project: display
ms.assetid: 3ebdf120-ecdd-474b-961d-958179cf30e0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenProtectedSessionFromNtHandle method [Display Devices], D3DKMTOpenProtectedSessionFromNtHandle, display.d3dkmtopenprotectedsessionfromnthandle, d3dkmthk/D3DKMTOpenProtectedSessionFromNtHandle
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
-	D3DKMTOpenProtectedSessionFromNtHandle
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenProtectedSessionFromNtHandle function


## -description


Used to open a protected session from the NT handle.
			
            


## -syntax


````
NTSTATUS  D3DKMTOpenProtectedSessionFromNtHandle(
  _Inout_ D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE  *D3dkmt_openprotectedsessionfromnthandle
);
````


## -parameters





#### - D3dkmt_openprotectedsessionfromnthandle [in, out]

Holds information to open the protected session.


## -returns


Returns STATUS_SUCCESS if completed successfully.


