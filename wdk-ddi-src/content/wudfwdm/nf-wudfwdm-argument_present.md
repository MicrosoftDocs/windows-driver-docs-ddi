---
UID: NF:wudfwdm.ARGUMENT_PRESENT
title: ARGUMENT_PRESENT macro
author: windows-driver-content
description: The ARGUMENT_PRESENT macro takes an argument pointer and returns FALSE if the pointer is NULL. Otherwise, it returns TRUE.
old-location: kernel\argument_present.htm
tech.root: kernel
ms.assetid: 00b9c218-8ae7-4624-be6b-6b6b2f83764a
ms.date: 4/30/2018
ms.keywords: ARGUMENT_PRESENT, ARGUMENT_PRESENT macro [Kernel-Mode Driver Architecture], k106_a835da4a-e4c4-4c39-8b20-c7ef88f2ab6b.xml, kernel.argument_present, wudfwdm/ARGUMENT_PRESENT
ms.topic: macro
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntdef.h
req.target-type: Desktop
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
-	wudfwdm.h
api_name:
-	ARGUMENT_PRESENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# ARGUMENT_PRESENT macro


## -description


The <b>ARGUMENT_PRESENT</b> macro evaluates to <b>FALSE</b> if the value of <i>ArgumentPointer</i> is <b>NULL</b>.  Otherwise, it evaluates to <b>TRUE</b>.


## -parameters




### -param ArgumentPointer [in]

Specifies the value of the pointer argument to be tested.


## -remarks



This macro can be called in conditional code to determine whether an optional argument has been passed in a call. 



