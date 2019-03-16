---
UID: NF:engextcpp.ExtRemoteList.ExtRemoteList(ULONG64,ULONG,bool)
title: ExtRemoteList::ExtRemoteList(ULONG64,ULONG,bool) (engextcpp.h)
description: The ExtRemoteList constructors create a new instance that wraps a singly-linked or doubly-linked list.
old-location: debugger\extremotelist_extremotelist_ulong64.htm
tech.root: debugger
ms.assetid: c23487bb-c385-4633-b27c-12a49492f339
ms.date: 05/03/2018
ms.keywords: ExtRemoteList, ExtRemoteList class [Windows Debugging],ExtRemoteList constructor, ExtRemoteList constructor [Windows Debugging], ExtRemoteList constructor [Windows Debugging],ExtRemoteList class, ExtRemoteList.ExtRemoteList, ExtRemoteList.ExtRemoteList(ULONG64,ULONG,bool), ExtRemoteList::ExtRemoteList, ExtRemoteList::ExtRemoteList(ULONG64,ULONG,bool), debugger.extremotelist_extremotelist_ulong64
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
- ExtRemoteList.ExtRemoteList
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteList::ExtRemoteList(ULONG64,ULONG,bool)


## -description


The <b>ExtRemoteList</b> constructors create a new instance that wraps a singly-linked or doubly-linked list.


## -parameters




### -param Head [in]

The location, in the target's memory, of the head of the list.  The head is not considered to be an item in the list.  The type of the head of the list is SINGLE_LIST_ENTRY or LIST_ENTRY.


### -param LinkOffset [in]

The offset from the beginning of a list item to the pointer to the next item in the list.  This is the offset of the SINGLE_LIST_ENTRY or LIST_ENTRY structure embedded within the list item structure.


### -param Double [in]

Specifies whether the list is singly-linked or doubly-linked.  If <i>Double</i> is <code>true</code>, the list is doubly-linked.  If <i>Double</i> is <code>false</code>, the list is singly-linked.


## -remarks



For more information about the SINGLE_LIST_ENTRY and LIST_ENTRY structures, see the Windows Driver Kit (WDK) documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544114">ExtRemoteList</a>



<a href="https://msdn.microsoft.com/db670175-ad3b-4bed-b9ad-625494319256">ExtRemoteList::ExtRemoteList (ExtRemoteData)</a>
 

 

