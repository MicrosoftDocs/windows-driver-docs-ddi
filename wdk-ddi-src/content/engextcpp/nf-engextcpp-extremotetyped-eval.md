---
UID: NF:engextcpp.ExtRemoteTyped.Eval
title: ExtRemoteTyped::Eval
description: The Eval method returns typed data that is the result of evaluating an expression.
old-location: debugger\extremotetyped_eval.htm
tech.root: debugger
ms.assetid: f54c7dfd-1997-4056-b20a-94438552aeca
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_84c338f5-8b46-4c8b-80f0-f1f02f3b691e.xml, Eval, Eval method [Windows Debugging], Eval method [Windows Debugging],ExtRemoteTyped interface, ExtRemoteTyped interface [Windows Debugging],Eval method, ExtRemoteTyped.Eval, ExtRemoteTyped::Eval, debugger.extremotetyped_eval
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.Eval
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::Eval


## -description


The <b>Eval</b> method returns typed data that is the result of evaluating an expression.


## -parameters




### -param Expr [in]

The expression to evaluate. <i>Expr</i> is evaluated using the default expression evaluator.


## -returns



<b>Eval</b> returns a new <b>ExtRemoteData</b> object that represents the typed data that is the result of evaluating the expression.



