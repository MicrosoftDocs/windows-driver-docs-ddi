---
UID: NF:d3dkmthk.D3DKMTCreateHwContext
title: D3DKMTCreateHwContext function
author: windows-driver-content
description: Used to create a new hardware context.
old-location: display\d3dkmtcreatehwcontext.htm
old-project: display
ms.assetid: 147F46A9-1182-4480-8886-7C39F940EA7D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateHwContext method [Display Devices], D3DKMTCreateHwContext, d3dkmthk/D3DKMTCreateHwContext, display.d3dkmtcreatehwcontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
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
-	D3DKMTCreateHwContext
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateHwContext function


## -description


Used to create a new hardware context.


## -syntax


````
NTSTATUS D3DKMTCreateHwContext(
  _Inout_ D3DKMT_CREATEHWCONTEXT *createHwContext
);
````


## -parameters





#### - createHwContext [in, out]

A structure holding the information needed to create a new hardware context.


## -returns


Returns STATUS_SUCCESS if called successfully. 


