---
UID: NF:engextcpp.ExtRemoteTyped.ExtRemoteTyped(const DEBUG_TYPED_DATA)
title: ExtRemoteTyped::ExtRemoteTyped(const DEBUG_TYPED_DATA) (engextcpp.h)
description: The ExtRemoteTyped constructor creates a new instance of the ExtRemoteTyped class.
old-location: debugger\extremotetyped_extremotetyped_debug_typed_data.htm
tech.root: debugger
ms.assetid: 6cfe4258-be66-49fd-b154-124951ed0dd1
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging],ExtRemoteTyped constructor, ExtRemoteTyped constructor [Windows Debugging], ExtRemoteTyped constructor [Windows Debugging],ExtRemoteTyped class, ExtRemoteTyped.ExtRemoteTyped, ExtRemoteTyped.ExtRemoteTyped(DEBUG_TYPED_DATA*), ExtRemoteTyped.ExtRemoteTyped(const DEBUG_TYPED_DATA), ExtRemoteTyped::ExtRemoteTyped, ExtRemoteTyped::ExtRemoteTyped(const DEBUG_TYPED_DATA), debugger.extremotetyped_extremotetyped_debug_typed_data
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

# ExtRemoteTyped::ExtRemoteTyped(const DEBUG_TYPED_DATA)


## -description


The <b>ExtRemoteTyped</b> constructor creates a new instance of the <b>ExtRemoteTyped</b> class.


## -parameters




### -param Typed [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a> structure that describes the data and type to be represented by this object.


## -remarks



The typed data can also be set or changed using the following methods: 
	<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>


</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-extremotetyped">ExtRemoteTyped::ExtRemoteTyped</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(constextremotetyped_)">ExtRemoteTyped::ExtRemoteTyped (ExtRemoteTyped)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr)">ExtRemoteTyped::ExtRemoteTyped (PCSTR)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr_ulong64)">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-extremotetyped(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::ExtRemoteTyped (PCSTR, ULONG64, bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(bool_ulong64_ulong_ulong64)">ExtRemoteTyped::Set(bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64_bool_pulong64_pcstr)">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set(pcstr_ulong64)">ExtRemoteTyped::Set(pcstr ulong64)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-set">ExtRemoteTyped::Set(pcstr)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetypedlist-extremotetypedlist(extremotedata__pcstr_pcstr_ulong64_ulong_pulong64_bool)">ExtRemoteTypedList</a>
 

 

