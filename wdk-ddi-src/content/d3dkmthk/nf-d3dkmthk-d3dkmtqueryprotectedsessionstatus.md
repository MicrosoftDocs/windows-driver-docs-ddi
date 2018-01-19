---
UID: NF:d3dkmthk.D3DKMTQueryProtectedSessionStatus
title: D3DKMTQueryProtectedSessionStatus function
author: windows-driver-content
description: Used to query the status of the protected session.
old-location: display\d3dkmtqueryprotectedsessionstatus.htm
old-project: display
ms.assetid: 787f20a4-51b6-44e3-aefb-2dc529359545
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTQueryProtectedSessionStatus
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
req.alt-api: D3DKMTQueryProtectedSessionStatus
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

# D3DKMTQueryProtectedSessionStatus function



## -description
Used to query the status of the protected session.
			
            



## -syntax

````
NTSTATUS  D3DKMTQueryProtectedSessionStatus(
   D3DKMT_QUERYPROTECTEDSESSIONSTATUS  D3dkmt_queryprotectedsessionstatus
);
````


## -parameters

### -param D3dkmt_queryprotectedsessionstatus 

Holds the information for the status of the protected session.


## -returns

Returns STATUS_SUCCESS if completed successfully.


## -remarks
