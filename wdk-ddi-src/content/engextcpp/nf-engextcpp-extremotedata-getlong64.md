---
UID: NF:engextcpp.ExtRemoteData.GetLong64
title: ExtRemoteData::GetLong64 (engextcpp.h)
description: The GetLong64 method returns a LONG64 version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong64.htm
tech.root: debugger
ms.assetid: dd6f051a-d287-4cb9-8c53-928415e0f152
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_4b2bf03d-7a55-4cee-826b-2b384972392f.xml, ExtRemoteData class [Windows Debugging],GetLong64 method, ExtRemoteData.GetLong64, ExtRemoteData::GetLong64, GetLong64, GetLong64 method [Windows Debugging], GetLong64 method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getlong64
f1_keywords:
 - "engextcpp/ExtRemoteData.GetLong64"
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
- ExtRemoteData.GetLong64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetLong64


## -description


The <b>GetLong64</b> method returns a LONG64 version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -returns



<b>GetLong64</b> returns the LONG64 version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(LONG64)</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlong64">ExtRemoteData::GetLong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulong">ExtRemoteData::GetUlong</a>
 

 

