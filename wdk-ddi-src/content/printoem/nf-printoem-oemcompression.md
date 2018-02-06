---
UID: NF:printoem.OEMCompression
title: OEMCompression function
author: windows-driver-content
description: OEMCompression function
old-location: print\oemcompression.htm
old-project: print
ms.assetid: e5246411-aa43-436f-b5e7-d7305ce659c9
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMCompression, print.oemcompression, print_obsoletefunctions_e5318981-34d5-4d97-97fe-c0bdf9ca8f97.xml, printoem/OEMCompression, OEMCompression function [Print Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMCompression
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMCompression function


## -description




## -syntax


````
INT APIENTRY OEMCompression(
        PDEVOBJ                        pdevobj,
  _In_  _reads_bytes_(dwInLen) PBYTE   pInBuf,
  _Out_ _writes_bytes_(dwOutLen) PBYTE pOutBuf,
        DWORD                          dwInLen,
        DWORD                          dwOutLen
);
````


## -parameters




### -param pdevobj



### -param pInBuf [in]



### -param pOutBuf [out]



### -param dwInLen



### -param dwOutLen


