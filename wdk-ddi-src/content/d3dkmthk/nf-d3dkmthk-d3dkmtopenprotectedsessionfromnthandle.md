---
UID: NF:d3dkmthk.D3DKMTOpenProtectedSessionFromNtHandle
title: D3DKMTOpenProtectedSessionFromNtHandle function
author: windows-driver-content
description: Used to open a protected session from the NT handle.
old-location: display\d3dkmtopenprotectedsessionfromnthandle.htm
tech.root: display
ms.assetid: 3ebdf120-ecdd-474b-961d-958179cf30e0
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTOpenProtectedSessionFromNtHandle, D3DKMTOpenProtectedSessionFromNtHandle method [Display Devices], d3dkmthk/D3DKMTOpenProtectedSessionFromNtHandle, display.d3dkmtopenprotectedsessionfromnthandle
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
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
api_name:
-	D3DKMTOpenProtectedSessionFromNtHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTOpenProtectedSessionFromNtHandle function


## -description


Used to open a protected session from the NT handle.
			
            


## -parameters




### -param Arg1






#### - D3dkmt_openprotectedsessionfromnthandle [in, out]

Holds information to open the protected session.


## -returns



Returns STATUS_SUCCESS if completed successfully.



