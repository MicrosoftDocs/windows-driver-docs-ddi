---
UID: NF:engextcpp.ExtRemoteTyped.Set(bool,ULONG64,ULONG,ULONG64)
title: ExtRemoteTyped::Set(bool,ULONG64,ULONG,ULONG64) (engextcpp.h)
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_bool.htm
tech.root: debugger
ms.assetid: e75c17d2-fdf7-4dba-9892-74c764956924
ms.date: 05/03/2018
keywords: ["ExtRemoteTyped::Set(bool,ULONG64,ULONG,ULONG64)"]
ms.keywords: ExtRemoteTyped class [Windows Debugging],Set method, ExtRemoteTyped.Set, ExtRemoteTyped.Set(bool,ULONG64,ULONG,ULONG64), ExtRemoteTyped::Set, ExtRemoteTyped::Set(bool,ULONG64,ULONG,ULONG64), Set, Set method [Windows Debugging], Set method [Windows Debugging],ExtRemoteTyped class, debugger.extremotetyped_set_bool
f1_keywords:
 - "engextcpp/ExtRemoteTyped.Set"
 - "ExtRemoteTyped.Set"
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
- ExtRemoteTyped.Set
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::Set(bool,ULONG64,ULONG,ULONG64)


## -description


The <b>Set</b> method sets the typed data represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> object.


## -parameters




### -param PtrTo 
[in]
Specifies whether or not to set the <b>ExtRemoteTyped</b> instance to the specified typed data, or to a pointer to the specified typed data.  If <i>PtrTo</i> is <code>true</code>, the <b>ExtRemoteTyped</b> instance will be a pointer to the typed data.


### -param TypeModBase 
[in]
The base address of the module to which the type belongs.


### -param TypeId 
[in]
The type ID of the type.


### -param Offset 
[in]
Specifies the location of the data in the target's memory.


## -returns



This method does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set (PCSTR)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-setprint">ExtRemoteTyped::SetPrint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList</a>
 

 

