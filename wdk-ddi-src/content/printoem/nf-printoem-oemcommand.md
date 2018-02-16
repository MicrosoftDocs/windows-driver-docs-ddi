---
UID: NF:printoem.OEMCommand
title: OEMCommand function
author: windows-driver-content
description: OEMCommand function
old-location: print\oemcommand.htm
old-project: print
ms.assetid: 67f75696-dee4-43ec-90fd-96fd1a91ec16
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print_obsoletefunctions_f6d1a0f9-6560-4e4c-9826-c2714b7c1ad3.xml, print.oemcommand, OEMCommand, printoem/OEMCommand, OEMCommand function [Print Devices]
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
-	OEMCommand
product: Windows
targetos: Windows
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

