---
UID: NF:engextcpp.ExtRemoteData.Set(constDEBUG_TYPED_DATA)
title: ExtRemoteData::Set(const DEBUG_TYPED_DATA) (engextcpp.h)
description: The Set method sets the region of the target's memory represented by the ExtRemoteData object.
old-location: debugger\extremotedata_set_typed.htm
tech.root: debugger
ms.assetid: a335f881-7b6f-4069-87fe-c036867b0c77
ms.date: 05/03/2018
keywords: ["ExtRemoteData::Set(const DEBUG_TYPED_DATA)"]
ms.keywords: ExtRemoteData class [Windows Debugging],Set method, ExtRemoteData.Set, ExtRemoteData.Set(const DEBUG_TYPED_DATA), ExtRemoteData.Set(const DEBUG_TYPED_DATA*), ExtRemoteData::Set, ExtRemoteData::Set(const DEBUG_TYPED_DATA), Set, Set method [Windows Debugging], Set method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_set_typed
f1_keywords:
 - "engextcpp/ExtRemoteData.Set"
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
- ExtRemoteData.Set
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# ExtRemoteData::Set(const DEBUG_TYPED_DATA)


## -description


The <b>Set</b> method sets the region of the target's memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.


## -parameters




### -param Typed [in]

Specifies the region of memory by using a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a> structure.


## -remarks



The <b>Set</b> method will read the contents of the specified region of  memory and cache the data.  The data can be retrieved using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a> or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set (Offset, Bytes)</a>
 

 

