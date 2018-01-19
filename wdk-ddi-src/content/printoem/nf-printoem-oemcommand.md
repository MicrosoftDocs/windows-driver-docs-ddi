---
UID: NF:printoem.OEMCommand
title: OEMCommand function
author: windows-driver-content
description: OEMCommand function
old-location: print\oemcommand.htm
old-project: print
ms.assetid: 67f75696-dee4-43ec-90fd-96fd1a91ec16
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMCommand
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
req.alt-api: OEMCommand
req.alt-loc: printoem.h
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMCommand function



## -description

## -syntax

````
DWORD APIENTRY OEMCommand(
       PDEVOBJ                         pdevobj,
       DWORD                           dwIndex,
  _In_ _reads_bytes_opt_(cbSize) PVOID pData,
       DWORD                           cbSize
);
````


## -parameters

### -param pdevobj 


### -param dwIndex 


### -param pData [in]


### -param cbSize 


## -remarks
