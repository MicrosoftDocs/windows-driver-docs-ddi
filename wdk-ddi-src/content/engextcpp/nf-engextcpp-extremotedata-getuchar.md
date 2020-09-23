---
UID: NF:engextcpp.ExtRemoteData.GetUchar
title: ExtRemoteData::GetUchar (engextcpp.h)
description: The GetUChar method returns a UCHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getuchar.htm
tech.root: debugger
ms.assetid: 2c4b7f40-210a-44fa-b7d4-150355d6b75b
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetUchar"]
ms.keywords: EngExtCpp_Ref_687a7887-560a-4565-8417-ec46cc1ee254.xml, ExtRemoteData class [Windows Debugging],GetUchar method, ExtRemoteData.GetUchar, ExtRemoteData::GetUchar, GetUchar, GetUchar method [Windows Debugging], GetUchar method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getuchar
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
 - ExtRemoteData::GetUchar
 - engextcpp/ExtRemoteData::GetUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetUchar
---

# ExtRemoteData::GetUchar


## -description

The <b>GetUChar</b> method returns a UCHAR version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetUChar</b> returns the UCHAR version of the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(UCHAR)</code>.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getchar">ExtRemoteData::GetChar</a>



<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>