---
UID: NF:engextcpp.ExtRemoteTyped.Dereference
title: ExtRemoteTyped::Dereference (engextcpp.h)
description: The Dereference method returns the typed data that is pointed to by the typed data represented by this object.
old-location: debugger\extremotetyped_dereference.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::Dereference"]
ms.keywords: Dereference, Dereference method [Windows Debugging], Dereference method [Windows Debugging],ExtRemoteTyped interface, EngExtCpp_Ref_d195c66d-88c1-4099-a227-0dd86d9d67e2.xml, ExtRemoteTyped interface [Windows Debugging],Dereference method, ExtRemoteTyped.Dereference, ExtRemoteTyped::Dereference, debugger.extremotetyped_dereference
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtRemoteTyped::Dereference
 - engextcpp/ExtRemoteTyped::Dereference
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteTyped.Dereference
---

# ExtRemoteTyped::Dereference


## -description

The <b>Dereference</b> method returns the typed data that is pointed to by the typed data represented by this object.

## -returns

<b>Dereference</b> returns a new <b>ExtRemoteData</b> object that represents the typed data pointed to by the typed data represented by this object.

## -remarks

If the typed data represented by this object is an array, the first element in the array is returned.

