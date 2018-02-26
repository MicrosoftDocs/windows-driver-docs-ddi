---
UID: NF:d3dkmthk.D3DKMTExtractBundleObject
title: D3DKMTExtractBundleObject function
author: windows-driver-content
description: Used to extract the bundle object.
old-location: display\d3dkmtextractbundleobject.htm
old-project: display
ms.assetid: f3193d5b-084f-4df1-9688-26ba5a964cca
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , 3, B, D, D3DKMTExtractBundleObject, D3DKMTExtractBundleObject method [Display Devices], E, K, M, O, T, a, b, c, d, d3dkmthk/D3DKMTExtractBundleObject, display.d3dkmtextractbundleobject, e, j, l, n, r, t, u, x"
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
-	D3DKMTExtractBundleObject
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTExtractBundleObject function


## -description



			
            Used to extract the bundle object.


## -syntax


````
NTSTATUS  D3DKMTExtractBundleObject(
  _Inout_ D3DKMT_EXTRACTBUNDLEOBJECT  *D3dkmt_extractbundleobject
);
````


## -parameters






#### - D3dkmt_extractbundleobject [in, out]

Holds information to extract the bundle object.


## -returns



Returns STATUS_SUCCESS if completed successfully. 



