---
UID: NF:engextcpp.ExtRemoteTyped.Field
title: ExtRemoteTyped::Field (engextcpp.h)
description: The Field method returns the typed data for a member in the typed data that is represented by this object.
old-location: debugger\extremotetyped_field.htm
tech.root: debugger
ms.assetid: be662551-c4d3-4979-8a9b-c913fb6bd336
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_a235495d-4e04-4f57-acd4-0e4cdeabee14.xml, ExtRemoteTyped interface [Windows Debugging],Field method, ExtRemoteTyped.Field, ExtRemoteTyped::Field, Field, Field method [Windows Debugging], Field method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_field
f1_keywords:
 - "engextcpp/ExtRemoteTyped.Field"
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
- ExtRemoteTyped.Field
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::Field


## -description


The <b>Field</b> method returns the typed data for a member in the typed data that is represented by this object.


## -parameters




### -param Field [in]

The name of the member whose typed data is requested.  Sub-members can be specified using a dot-separated path (for example, <b>mymember.mysubmember</b>).  Pointers on this dot-separated path will automatically be dereferenced. However, a dot operator (<b>.</b>) should still be used here instead of the usual C pointer dereference operator (<b>-></b>).


## -returns



<b>Field</b> returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified member.



