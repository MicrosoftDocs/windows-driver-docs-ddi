---
UID: NF:engextcpp.ExtRemoteData.Set(ULONG64,ULONG)
title: ExtRemoteData::Set (engextcpp.h)
description: The Set method sets the region of the target's memory represented by the ExtRemoteData object.
old-location: debugger\extremotedata_set_offset_bytes.htm
tech.root: debugger
ms.assetid: 50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5
ms.date: 04/24/2018
keywords: ["ExtRemoteData::Set"]
ms.keywords: ExtRemoteData interface [Windows Debugging],Set method, ExtRemoteData.Set, ExtRemoteData::Set, ExtRemoteData::Set(ULONG64,ULONG), Set, Set method [Windows Debugging], Set method [Windows Debugging],ExtRemoteData interface, debugger.extremotedata_set_offset_bytes, engextcpp/ExtRemoteData::Set
f1_keywords:
 - "engextcpp/ExtRemoteData.Set"
 - "ExtRemoteData.Set"
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
---

# ExtRemoteData::Set


## -description


The <b>Set</b> method sets the region of the target's memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.


## -parameters




#### - Offset [in]

Location of the beginning of the memory region in the target's virtual address space.


#### - Bytes [in]

Number of bytes in the memory region.


## -returns



This method does not return a value.




## -remarks



The <b>Set</b> method will read the contents of the specified region of memory and cache the data.  The data can be retrieved using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a> or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set (Typed)</a>
 

 

