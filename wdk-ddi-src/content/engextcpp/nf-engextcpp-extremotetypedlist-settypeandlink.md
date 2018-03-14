---
UID: NF:engextcpp.ExtRemoteTypedList.SetTypeAndLink
title: ExtRemoteTypedList::SetTypeAndLink method
author: windows-driver-content
description: The SetTypeAndLink method sets the type information for the typed list.
old-location: debugger\extremotetypedlist_settypeandlink.htm
old-project: debugger
ms.assetid: f6e2d8e3-294d-45d8-8fc6-33af3a746244
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_8867c503-5983-465c-bfb6-f13b21d325cc.xml, ExtRemoteTypedList, ExtRemoteTypedList class [Windows Debugging], SetTypeAndLink method, ExtRemoteTypedList::SetTypeAndLink, SetTypeAndLink method [Windows Debugging], SetTypeAndLink method [Windows Debugging], ExtRemoteTypedList class, SetTypeAndLink,ExtRemoteTypedList.SetTypeAndLink, debugger.extremotetypedlist_settypeandlink
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
-	ExtRemoteTypedList.SetTypeAndLink
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTypedList::SetTypeAndLink method


## -description


The <b>SetTypeAndLink</b> method sets the type information for the typed list.


## -syntax


````
void SetTypeAndLink(
  [in]                PCSTR    Type,
  [in]                PCSTR    LinkField,
  [in]                ULONG64  TypeModBase,
  [in]                ULONG    TypeId,
  [in, out, optional] PULONG64 CacheCookie
);
````


## -parameters




### -param Type [in]

The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <i>TypeId</i> is not zero, <i>Type</i> is not used.


### -param LinkField [in]

The name of the field of the typed data structure  that contains the pointer to the next list item.  This is either the SINGLE_LIST_ENTRY structure or the LIST_ENTRY structure embedded in the list item.


### -param TypeModBase [in]

The location in the target's memory of the base address of the module that contains the type specified by <i>TypeId</i>.  If <i>TypeId</i> is zero, <i>TypeModBase</i> is not used.


### -param TypeId [in]

The type ID of the type relative to the module specified by <i>TypeModBase</i>.  If <i>TypeId</i> is zero, <i>Type</i> is used to specify the type of the list items.


### -param CacheCookie [in, out, optional]

The cache cookie to use for caching the type information.  If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for the type information each time.

For more information about <i>CacheCookie</i>, see the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.


## -returns



None




## -remarks



For more information about the SINGLE_LIST_ENTRY and LIST_ENTRY structures, see the Windows Driver Kit documentation.




## -see-also

<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set(pcstr)</a>



<a href="..\engextcpp\nf-engextcpp-extbuffer-set.md">ExtRemoteTyped::Set(bool)</a>



 

 


