---
UID: NF:d3dkmthk.D3DKMTQueryProtectedSessionInfoFromNtHandle
title: D3DKMTQueryProtectedSessionInfoFromNtHandle function
author: windows-driver-content
description: Used to get information on the protected session.
old-location: display\d3dkmtqueryprotectedsessioninfofromnthandle.htm
old-project: display
ms.assetid: 04eff7e1-1ac3-4622-a837-1ea6aad97329
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTQueryProtectedSessionInfoFromNtHandle
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
req.alt-api: D3DKMTQueryProtectedSessionInfoFromNtHandle
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTQueryProtectedSessionInfoFromNtHandle function



## -description
Used to get information on the protected session.
			
            



## -syntax

````
NTSTATUS  D3DKMTQueryProtectedSessionInfoFromNtHandle(
   D3DKMT_QUERYPROTECTEDSESSIONINFOFROMNTHANDLE  D3dkmt_queryprotectedsessioninfofromnthandle
);
````


## -parameters

### -param D3dkmt_queryprotectedsessioninfofromnthandle 

Holds session information from the NT handle.


## -returns

Returns STATUS_SUCCESS when completed successfully.


## -remarks
