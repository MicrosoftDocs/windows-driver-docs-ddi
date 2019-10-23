---
UID: NF:engextcpp.ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR)
title: ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR) (engextcpp.h)
description: The ExtRemoteTyped constructor creates a new instance of the ExtRemoteTyped class.
old-location: debugger\extremotetyped_extremotetyped_pcstr_ulong64_bool.htm
tech.root: debugger
ms.assetid: 824f47da-2a56-4e09-b23a-a9754c1e2063
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging],ExtRemoteTyped constructor, ExtRemoteTyped constructor [Windows Debugging], ExtRemoteTyped constructor [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped.ExtRemoteTyped, ExtRemoteTyped.ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR), ExtRemoteTyped::ExtRemoteTyped, ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR), debugger.extremotetyped_extremotetyped_pcstr_ulong64_bool
ms.topic: method
f1_keywords:
 - "engextcpp/ExtRemoteTyped.ExtRemoteTyped"
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
- ExtRemoteTyped.ExtRemoteTyped
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteTyped::ExtRemoteTyped(PCSTR,ULONG64,bool,PULONG64,PCSTR)


## -description


The <b>ExtRemoteTyped</b> constructor creates a new instance of the <b>ExtRemoteTyped</b> class.


## -parameters




### -param Type [in]

An expression that evaluates to the desired symbol.  This expression is evaluated by the default expression evaluator.


### -param Offset [in]

The location of the data in the target's virtual address space.



### -param PtrTo [in]

Specifies whether or not to set the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a> instance to the specified typed data, or to a pointer to the specified typed data. If <i>PtrTo</i> is true, the <b>ExtRemoteTyped</b> instance will contain a pointer to the typed data. 



### -param CacheCookie [in, out, optional]

The cache cookie to use for caching type information. If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for type information each time.


For more information about <i>CacheCookie</i>, see the following methods:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>


</li>
</ul>

### -param LinkField [in, optional]

The name of a field in the typed data that contains the pointer to the next item in a list. <i>LinkField</i> should be set if <i>CacheCookie</i> is being used for the first time and will later be used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList</a>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped">ExtRemoteTyped::ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(constdebug_typed_data)">ExtRemoteTyped::ExtRemoteTyped (DEBUG_TYPED_DATA)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(constextremotetyped_)">ExtRemoteTyped::ExtRemoteTyped (ExtRemoteTyped)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr)">ExtRemoteTyped::ExtRemoteTyped (PCSTR)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr_ulong64)">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList</a>
 

 

