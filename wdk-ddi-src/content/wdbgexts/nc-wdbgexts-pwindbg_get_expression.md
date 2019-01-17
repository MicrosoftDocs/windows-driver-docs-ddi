---
UID: NC:wdbgexts.PWINDBG_GET_EXPRESSION
title: PWINDBG_GET_EXPRESSION
description: The PWINDBG_GET_EXPRESSION (GetExpression) function returns the value of expression. The expression is evaluated using the current expression evaluator, and can contain aliases.
old-location: debugger\getexpression.htm
tech.root: debugger
ms.assetid: 20d75838-6dbf-49a2-a0c9-a0c1ae74d7a6
ms.date: 05/03/2018
ms.keywords: GetExpression, GetExpression callback function [Windows Debugging], PWINDBG_GET_EXPRESSION, PWINDBG_GET_EXPRESSION callback, WdbgExts_Ref_666ae7de-7842-4ba8-9352-e79aefe24ba7.xml, debugger.getexpression, wdbgexts/GetExpression
ms.topic: callback
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
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	GetExpression
product:
- Windows
targetos: Windows
req.typenames: 
---

# PWINDBG_GET_EXPRESSION callback function


## -description


The <b>PWINDBG_GET_EXPRESSION</b> (<b>GetExpression</b>) function returns the value of <i>expression</i>. The expression is evaluated using the current expression evaluator, and can contain aliases.


## -parameters




### -param lpExpression








#### - expression [in]

Specifies the expression to evaluate.


## -returns



The value of the expression passed to <b>GetExpression</b>




## -remarks



The expression is evaluated by the current expression evaluator (either the MASM or C++ expression evaluator); see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552280">Numerical Expression Syntax</a> for details.  Aliases will be properly understood; see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a> for details.   

If KDEXT_64BIT is defined, this function returns a value of type ULONG64. Otherwise, it returns a value of type ULONG.



