---
UID: NF:printoem.OEMEnableDriver
title: OEMEnableDriver function
author: windows-driver-content
description: OEMEnableDriver function
old-location: print\oemenabledriver.htm
old-project: print
ms.assetid: 9ea2f53c-de27-4803-b09a-444180b796ac
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: printoem/OEMEnableDriver, OEMEnableDriver function [Print Devices], print_obsoletefunctions_4fe2a5f6-e5ad-4e35-b3d5-668e0cf96ee3.xml, OEMEnableDriver, print.oemenabledriver
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
-	OEMEnableDriver
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMEnableDriver function


## -description




## -syntax


````
DWORD APIENTRY OEMEnableDriver(
        DWORD                                 dwOemIntfVersion,
        DWORD                                 cbSize,
  _Out_ _writes_bytes_(cbSize) PDRVENABLEDATA pded
);
````


## -parameters




### -param dwOemIntfVersion



### -param cbSize



### -param pded [out]


