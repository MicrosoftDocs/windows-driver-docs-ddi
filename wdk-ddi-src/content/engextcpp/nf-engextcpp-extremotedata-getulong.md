---
UID: NF:engextcpp.ExtRemoteData.GetUlong
title: ExtRemoteData::GetUlong (engextcpp.h)
description: The GetUlong method returns a ULONG version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulong.htm
tech.root: debugger
ms.assetid: ce25b52e-5ac7-470d-902b-f45350718dff
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetUlong"]
ms.keywords: EngExtCpp_Ref_41a112c3-0350-4e54-981c-b5c11697ef2d.xml, ExtRemoteData class [Windows Debugging],GetUlong method, ExtRemoteData.GetUlong, ExtRemoteData::GetUlong, GetUlong, GetUlong method [Windows Debugging], GetUlong method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getulong
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
 - ExtRemoteData::GetUlong
 - engextcpp/ExtRemoteData::GetUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetUlong
---

# ExtRemoteData::GetUlong


## -description

The <b>GetUlong</b> method returns a ULONG version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetUlong</b> returns the ULONG version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(ULONG)</code>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlong64">ExtRemoteData::GetLong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulong">ExtRemoteData::GetUlong</a>

