---
UID: NF:engextcpp.ExtRemoteData.GetDouble
title: ExtRemoteData::GetDouble (engextcpp.h)
description: The GetDouble method returns a double version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getdouble.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetDouble"]
ms.keywords: EngExtCpp_Ref_8776e6fd-9e13-4502-a445-da65a8fcfe41.xml, ExtRemoteData class [Windows Debugging],GetDouble method, ExtRemoteData.GetDouble, ExtRemoteData::GetDouble, GetDouble, GetDouble method [Windows Debugging], GetDouble method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getdouble
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
 - ExtRemoteData::GetDouble
 - engextcpp/ExtRemoteData::GetDouble
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetDouble
---

# ExtRemoteData::GetDouble


## -description

The <b>GetDouble</b> method returns a <b>double</b> version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetDouble</b> returns the <b>double</b> version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(double)</code>.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getfloat">ExtRemoteData::GetFloat</a>
