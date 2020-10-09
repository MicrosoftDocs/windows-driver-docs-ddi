---
UID: NF:engextcpp.ExtRemoteData.GetUlongPtr
title: ExtRemoteData::GetUlongPtr (engextcpp.h)
description: The GetUlongPtr method returns an unsigned integer version (extended to ULONG64) of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulongptr.htm
tech.root: debugger
ms.assetid: 1a3a870b-9f50-4430-b4f4-6d877d2fac3e
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetUlongPtr"]
ms.keywords: EngExtCpp_Ref_22ba632d-a45b-40de-b8d7-269c917357d5.xml, ExtRemoteData class [Windows Debugging],GetUlongPtr method, ExtRemoteData.GetUlongPtr, ExtRemoteData::GetUlongPtr, GetUlongPtr, GetUlongPtr method [Windows Debugging], GetUlongPtr method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getulongptr
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
 - ExtRemoteData::GetUlongPtr
 - engextcpp/ExtRemoteData::GetUlongPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetUlongPtr
---

# ExtRemoteData::GetUlongPtr


## -description

The <b>GetUlongPtr</b> method returns an unsigned integer version (extended to ULONG64) of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.

## -returns

<b>GetUlongPtr</b> returns an unsigned integer version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, extended to ULONG64.

## -remarks

The size of the memory represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlongptr">ExtRemoteData::GetLongPtr</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulong">ExtRemoteData::GetUlong</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulong64">ExtRemoteData::GetUlong64</a>