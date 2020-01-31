---
UID: NF:engextcpp.ExtRemoteData.GetLongPtr
title: ExtRemoteData::GetLongPtr (engextcpp.h)
description: The GetLongPtr method returns a signed integer version (extended to LONG64) of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.
old-location: debugger\extremotedata_getlongptr.htm
tech.root: debugger
ms.assetid: 9f796af1-870b-4349-b86a-3c9d868662f6
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_3160f5ef-8983-40b4-a7f8-95a1a40d67ac.xml, ExtRemoteData class [Windows Debugging],GetLongPtr method, ExtRemoteData.GetLongPtr, ExtRemoteData::GetLongPtr, GetLongPtr, GetLongPtr method [Windows Debugging], GetLongPtr method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getlongptr
f1_keywords:
 - "engextcpp/ExtRemoteData.GetLongPtr"
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
- ExtRemoteData.GetLongPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetLongPtr


## -description


The <b>GetLongPtr</b> method returns a signed integer version (extended to LONG64) of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.  The size of the unsigned integer from the target is the same size as a pointer on the target. 


## -returns



<b>GetLongPtr</b> returns a signed integer version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, extended to LONG64.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlong">ExtRemoteData::GetLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getlong64">ExtRemoteData::GetLong64</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getulongptr">ExtRemoteData::GetUlongPtr</a>
 

 

