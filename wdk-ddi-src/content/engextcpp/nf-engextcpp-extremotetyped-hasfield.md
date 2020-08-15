---
UID: NF:engextcpp.ExtRemoteTyped.HasField
title: ExtRemoteTyped::HasField (engextcpp.h)
description: The HasField method determines if the type of the data represented by this object contains the specified member.
old-location: debugger\extremotetyped_hasfield.htm
tech.root: debugger
ms.assetid: c206d8e7-1a90-4866-868b-20275a52e2dd
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::HasField"]
ms.keywords: EngExtCpp_Ref_8ce2c346-a92a-45ef-8baa-f1c42670aca6.xml, ExtRemoteTyped interface [Windows Debugging],HasField method, ExtRemoteTyped.HasField, ExtRemoteTyped::HasField, HasField, HasField method [Windows Debugging], HasField method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_hasfield
f1_keywords:
 - "engextcpp/ExtRemoteTyped.HasField"
 - "ExtRemoteTyped.HasField"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteTyped.HasField
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::HasField


## -description


The <b>HasField</b> method determines if the type of the data represented by this object contains the specified member.


## -parameters




### -param Field 
[in]
The name of the member.  The name of the member is a dot-separated path and can contain sub-members (for example, <b>mymember.mysubmember</b>).  Pointers on this dot-separated path will automatically be dereferenced. However, a dot operator (<b>.</b>) should still be used here instead of the usual C pointer dereference operator (<b>-></b>).


## -returns



<b>HasField</b> returns <code>true</code> if the typed data contains the member; <code>false</code> otherwise.



