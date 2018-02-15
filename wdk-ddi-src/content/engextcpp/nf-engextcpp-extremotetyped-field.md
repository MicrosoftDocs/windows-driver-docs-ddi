---
UID: NF:engextcpp.ExtRemoteTyped.Field
title: ExtRemoteTyped::Field method
author: windows-driver-content
description: The Field method returns the typed data for a member in the typed data that is represented by this object.
old-location: debugger\extremotetyped_field.htm
old-project: debugger
ms.assetid: be662551-c4d3-4979-8a9b-c913fb6bd336
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ExtRemoteTyped, Field method [Windows Debugging], ExtRemoteTyped interface, ExtRemoteTyped::Field, Field method [Windows Debugging], EngExtCpp_Ref_a235495d-4e04-4f57-acd4-0e4cdeabee14.xml, ExtRemoteTyped interface [Windows Debugging], Field method, debugger.extremotetyped_field, Field
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteTyped.Field
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---

# ExtRemoteTyped::Field method


## -description


The <b>Field</b> method returns the typed data for a member in the typed data that is represented by this object.


## -syntax


````
ExtRemoteTyped Field(
  [in] PCSTR Field
);
````


## -parameters




### -param Field [in]

The name of the member whose typed data is requested.  Sub-members can be specified using a dot-separated path (for example, <b>mymember.mysubmember</b>).  Pointers on this dot-separated path will automatically be dereferenced. However, a dot operator (<b>.</b>) should still be used here instead of the usual C pointer dereference operator (<b>-&gt;</b>).


## -returns



<b>Field</b> returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified member.



