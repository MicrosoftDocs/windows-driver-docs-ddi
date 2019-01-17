---
UID: NF:wdbgexts.ListType
title: ListType function
description: The ListType function calls a specified callback function for every element in a linked list.
old-location: debugger\listtype.htm
tech.root: debugger
ms.assetid: 5c250438-8805-4f45-b08f-65ec87b3e61a
ms.date: 05/03/2018
ms.keywords: ListType, ListType function [Windows Debugging], WdbgExts_Ref_aa50fe48-2a66-4d5e-aec7-d225966cfab2.xml, debugger.listtype, wdbgexts/ListType
ms.topic: function
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	ListType
product:
- Windows
targetos: Windows
req.typenames: 
---

# ListType function


## -description


The <b>ListType</b> function calls a specified callback function for every element in a linked list.


## -parameters




### -param Type [in]

Specifies the name of the type of each entry in the linked list.


### -param Address [in]





#### If ListByFieldAddress is zero:

Specifies the address in the target's memory of the first entry in the linked list.



#### If ListByFieldAddress is 1:

Specifies the address in the target's memory of the member of the first entry that points to the next entry.


### -param ListByFieldAddress [in]

Specifies whether <i>Address</i> contains the base address of the first entry, or if it contains the address of the member of the first entry that points to the next entry.


### -param NextPointer [in]

Specifies the name of the member in the structure of type <i>Type</i> that contains a pointer to the next entry in the linked list.  <i>NextPointer</i> can be a period-separated path, for example, if <i>Type</i> is "nt!_ETHREAD", <i>NextPointer</i> could be "Tcb.ThreadListEntry.Flink".


### -param Context [in]

Specifies a pointer that is passed to the callback function specified by <i>CallbackRoutine</i> each time the callback function is called.


### -param CallbackRoutine [in]

Specifies a function that is called for each entry in the linked list.  The parameters passed to the function are the <i>Context</i> pointer and a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a> structure; the address of the entry is found in the <b>address</b> member of this structure.


## -returns



This function returns <b>TRUE</b> on success and <b>FALSE</b> on failure.



