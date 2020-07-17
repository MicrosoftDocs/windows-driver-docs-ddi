---
UID: NF:engextcpp.ExtRemoteData.GetLong
title: ExtRemoteData::GetLong (engextcpp.h)
description: The GetLong method returns a LONG version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong.htm
tech.root: debugger
ms.assetid: 064f50e7-bae8-4c29-9802-47efdb749652
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetLong"]
ms.keywords: EngExtCpp_Ref_10a1810d-2e15-490a-baeb-8881106f41a6.xml, ExtRemoteData class [Windows Debugging],GetLong method, ExtRemoteData.GetLong, ExtRemoteData::GetLong, GetLong, GetLong method [Windows Debugging], GetLong method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getlong
f1_keywords:
 - "engextcpp/ExtRemoteData.GetLong"
 - "ExtRemoteData.GetLong"
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
- ExtRemoteData.GetLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetLong


## -description


The <b>GetLong</b> method returns a LONG version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -returns



<b>GetLong</b> returns the LONG version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by this <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(LONG)</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlong64">ExtRemoteData::GetLong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulong">ExtRemoteData::GetUlong</a>
 

 

