---
UID: NF:wdbgexts.WriteMsr
title: WriteMsr function
author: windows-driver-content
description: The WriteMsr function writes to a Model-Specific Register (MSR).
old-location: debugger\writemsr.htm
old-project: debugger
ms.assetid: a88c2c74-ab9a-4d9a-aeb7-d08bfe497da4
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: WdbgExts_Ref_faeb78e1-24a2-4210-94f9-4e468ba69181.xml, WriteMsr, WriteMsr function [Windows Debugging], dbgeng/WriteMsr, debugger.writemsr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
-	dbgeng.h
api_name:
-	WriteMsr
product: Windows
targetos: Windows
req.typenames: 
---

# WriteMsr function


## -description


The <b>WriteMsr</b> function writes to a Model-Specific Register (MSR). 


## -parameters




### -param MsrReg [in]

Specifies the ID number of the MSR.


### -param MsrValue [in]

Specifies the new value of the MSR.


## -returns



None




## -remarks



For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.



