---
UID: NF:engextcpp.ExtRemoteData.GetBoolean
title: ExtRemoteData::GetBoolean (engextcpp.h)
description: The GetBoolean method returns a Boolean version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getboolean.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetBoolean"]
ms.keywords: EngExtCpp_Ref_791b0934-9cb7-430a-8b80-d7fe4f458f49.xml, ExtRemoteData class [Windows Debugging],GetBoolean method, ExtRemoteData.GetBoolean, ExtRemoteData::GetBoolean, GetBoolean, GetBoolean method [Windows Debugging], GetBoolean method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getboolean
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
 - ExtRemoteData::GetBoolean
 - engextcpp/ExtRemoteData::GetBoolean
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetBoolean
---

# ExtRemoteData::GetBoolean


## -description

The <b>GetBoolean</b> method returns a Boolean version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetBoolean</b> returns the BOOLEAN version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(BOOLEAN)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOLEAN is one of these types.  For the C++ <b>bool</b> type, use <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getstdbool">ExtRemoteData::GetStdBool</a>.  For the BOOL type, use <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getw32bool">ExtRemoteData::GetW32Bool</a>.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getstdbool">ExtRemoteData::GetStdBool</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getw32bool">ExtRemoteData::GetW32Bool</a>
