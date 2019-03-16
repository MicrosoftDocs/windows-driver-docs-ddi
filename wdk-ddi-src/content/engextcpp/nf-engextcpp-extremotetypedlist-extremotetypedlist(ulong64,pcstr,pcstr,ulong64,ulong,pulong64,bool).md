---
UID: NF:engextcpp.ExtRemoteTypedList.ExtRemoteTypedList(ULONG64,PCSTR,PCSTR,ULONG64,ULONG,PULONG64,bool)
title: ExtRemoteTypedList::ExtRemoteTypedList(ULONG64,PCSTR,PCSTR,ULONG64,ULONG,PULONG64,bool) (engextcpp.h)
description: The ExtRemoteTypedList constructors create a new instance that wraps a typed singly-linked or doubly-linked list.
old-location: debugger\extremotetypedlist_extremotetypedlist_ulong64.htm
tech.root: debugger
ms.assetid: 32bf47a2-4c64-468a-a8e3-f3777a0f324d
ms.date: 05/03/2018
ms.keywords: ExtRemoteTypedList, ExtRemoteTypedList class [Windows Debugging],ExtRemoteTypedList constructor, ExtRemoteTypedList constructor [Windows Debugging], ExtRemoteTypedList constructor [Windows Debugging],ExtRemoteTypedList class, ExtRemoteTypedList.ExtRemoteTypedList, ExtRemoteTypedList.ExtRemoteTypedList(ULONG64,PCSTR,PCSTR,ULONG64,ULONG,PULONG64,bool), ExtRemoteTypedList::ExtRemoteTypedList, ExtRemoteTypedList::ExtRemoteTypedList(ULONG64,PCSTR,PCSTR,ULONG64,ULONG,PULONG64,bool), debugger.extremotetypedlist_extremotetypedlist_ulong64
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- engextcpp.hpp
api_name:
- ExtRemoteTypedList.ExtRemoteTypedList
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTypedList::ExtRemoteTypedList(ULONG64,PCSTR,PCSTR,ULONG64,ULONG,PULONG64,bool)


## -description


The <b>ExtRemoteTypedList</b> constructors create a new instance that wraps a typed singly-linked or doubly-linked list. 


## -parameters




### -param Head [in]

The location, in the target's memory, of the head of the list.  The head is not considered to be an item in the list.  The type of the head of the list is SINGLE_LIST_ENTRY or LIST_ENTRY.


### -param Type [in]

The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <i>TypeId</i> is not zero, <i>Type</i> is not used.


### -param LinkField [in]

The name of the field of the typed data structure that contains the pointer to the next list item.  This is either the SINGLE_LIST_ENTRY structure or the LIST_ENTRY structure embedded in the list item.


### -param TypeModBase [in]

The location in the target's memory of the base address of the module that contains the type specified by <i>TypeId</i>.  If <i>TypeId</i> is zero, <i>TypeModBase</i> is not used.


### -param TypeId [in]

The type ID of the type relative to the module specified by <i>TypeModBase</i>.  If <i>TypeId</i> is zero, <i>Type</i> is used to specify the type of the list items.


### -param CacheCookie [in, out, optional]

The cache cookie to use for caching the type information.  If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for the type information each time.


	  For more information about <i>CacheCookie</i>, see the following methods:
	  <ul>
<li>

<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>


</li>
<li>

<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>


</li>
</ul>



### -param Double [in]

Specifies whether the list is singly-linked or doubly-linked.  If <i>Double</i> is <code>true</code>, the list is doubly-linked.  If <i>Double</i> is <code>false</code>, the list is singly-linked.


## -see-also




<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>



<a href="https://msdn.microsoft.com/1d3ff060-39ef-4475-b161-a29c20a0e2c2">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>
 

 

