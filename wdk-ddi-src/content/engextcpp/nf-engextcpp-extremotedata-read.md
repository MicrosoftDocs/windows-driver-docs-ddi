---
UID: NF:engextcpp.ExtRemoteData.Read
title: ExtRemoteData::Read (engextcpp.h)
description: The Read method reads the contents of the target's memory, represented by the ExtRemoteData object, and then caches the data.
old-location: debugger\extremotedata_read.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteData::Read"]
ms.keywords: EngExtCpp_Ref_69230a7b-f83c-46fc-88c4-134b506540af.xml, ExtRemoteData class [Windows Debugging],Read method, ExtRemoteData.Read, ExtRemoteData::Read, Read, Read method [Windows Debugging], Read method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_read
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtRemoteData::Read
 - engextcpp/ExtRemoteData::Read
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData::Read
---

# ExtRemoteData::Read


## -description

The <b>Read</b> method reads the contents of the target's memory, represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, and then caches the data.

## -returns

This method does not return a value.

## -remarks

When the region of memory is specified either by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a> or <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a> methods, the contents are automatically read from the target and cached.  This method only needs to be called if the memory on the target might have changed.

The data can be retrieved using <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a> or one of the typed "get" methods.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata">ExtRemoteData::ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set">ExtRemoteData::Set(Offset Bytes)</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-set(constdebug_typed_data)">ExtRemoteData::Set(Typed)</a>

