---
UID: NF:printoem.OEMCommandCallback
title: OEMCommandCallback function
author: windows-driver-content
description: OEMCommandCallback function
old-location: print\oemcommandcallback.htm
old-project: print
ms.assetid: 0ac9c56d-f03d-4082-a7df-c21db12c0d74
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMCommandCallback, OEMCommandCallback function [Print Devices], print.oemcommandcallback, print_obsoletefunctions_e59bdbd7-9100-40b3-9e89-6d41cbc85f44.xml, printoem/OEMCommandCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMCommandCallback
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMCommandCallback function


## -description




## -syntax


````
INT APIENTRY OEMCommandCallback(
       PDEVOBJ                     pdevobj,
       DWORD                       dwCallbackID,
       DWORD                       dwCount,
  _In_ _reads_opt_(dwCount) PDWORD pdwParams
);
````


## -parameters




### -param pdevobj


### -param dwCallbackID


### -param dwCount


### -param pdwParams [in]

