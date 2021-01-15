---
UID: NF:engextcpp.ExtRemoteData.GetUshort
title: ExtRemoteData::GetUshort (engextcpp.h)
description: The GetUshort method returns a USHORT version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getushort.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetUshort"]
ms.keywords: EngExtCpp_Ref_5429785d-2f76-434d-96c6-4fa7298aa32e.xml, ExtRemoteData class [Windows Debugging],GetUshort method, ExtRemoteData.GetUshort, ExtRemoteData::GetUshort, GetUshort, GetUshort method [Windows Debugging], GetUshort method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getushort
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
 - ExtRemoteData::GetUshort
 - engextcpp/ExtRemoteData::GetUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData::GetUshort
---

# ExtRemoteData::GetUshort


## -description

The <b>GetUshort</b> method returns a USHORT version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetUshort</b> returns the USHORT version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(USHORT)</code>.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getshort">ExtRemoteData::GetShort</a>

