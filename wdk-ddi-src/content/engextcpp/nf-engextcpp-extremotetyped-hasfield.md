---
UID: NF:engextcpp.ExtRemoteTyped.HasField
title: ExtRemoteTyped::HasField method
author: windows-driver-content
description: The HasField method determines if the type of the data represented by this object contains the specified member.
old-location: debugger\extremotetyped_hasfield.htm
old-project: debugger
ms.assetid: c206d8e7-1a90-4866-868b-20275a52e2dd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_8ce2c346-a92a-45ef-8baa-f1c42670aca6.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], HasField method, ExtRemoteTyped::HasField, HasField method [Windows Debugging], HasField method [Windows Debugging], ExtRemoteTyped interface, HasField,ExtRemoteTyped.HasField, debugger.extremotetyped_hasfield
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
-	ExtRemoteTyped.HasField
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::HasField method


## -description


The <b>HasField</b> method determines if the type of the data represented by this object contains the specified member.


## -parameters




### -param Field [in]

The name of the member.  The name of the member is a dot-separated path and can contain sub-members (for example, <b>mymember.mysubmember</b>).  Pointers on this dot-separated path will automatically be dereferenced. However, a dot operator (<b>.</b>) should still be used here instead of the usual C pointer dereference operator (<b>-&gt;</b>).


## -returns



<b>HasField</b> returns <code>true</code> if the typed data contains the member; <code>false</code> otherwise.



