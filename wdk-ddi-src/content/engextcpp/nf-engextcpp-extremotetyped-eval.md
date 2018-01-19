---
UID: NF:engextcpp.ExtRemoteTyped.Eval
title: ExtRemoteTyped::Eval method
author: windows-driver-content
description: The Eval method returns typed data that is the result of evaluating an expression.
old-location: debugger\extremotetyped_eval.htm
old-project: debugger
ms.assetid: f54c7dfd-1997-4056-b20a-94438552aeca
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped::Eval, Eval
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTyped.Eval
req.alt-loc: engextcpp.hpp
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
req.typenames: *PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::Eval method



## -description
The <b>Eval</b> method returns typed data that is the result of evaluating an expression.



## -syntax

````
ExtRemoteData Eval(
  [in] PCSTR Expr
);
````


## -parameters

### -param Expr [in]

The expression to evaluate. <i>Expr</i> is evaluated using the default expression evaluator.


## -returns
<b>Eval</b> returns a new <b>ExtRemoteData</b> object that represents the typed data that is the result of evaluating the expression.


## -remarks
