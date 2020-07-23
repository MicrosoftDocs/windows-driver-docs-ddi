---
UID: NF:engextcpp.ExtRemoteData.GetChar
title: ExtRemoteData::GetChar (engextcpp.h)
description: The GetChar method returns a CHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getchar.htm
tech.root: debugger
ms.assetid: bf916e7c-f03b-4d02-8260-bc90e8957cc9
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetChar"]
ms.keywords: EngExtCpp_Ref_98ced053-a952-4c9f-af2b-0aab9d20e311.xml, ExtRemoteData class [Windows Debugging],GetChar method, ExtRemoteData.GetChar, ExtRemoteData::GetChar, GetChar, GetChar method [Windows Debugging], GetChar method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getchar
f1_keywords:
 - "engextcpp/ExtRemoteData.GetChar"
 - "ExtRemoteData.GetChar"
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
- ExtRemoteData.GetChar
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetChar


## -description


The <b>GetChar</b> method returns a CHAR version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -returns



<b>GetChar</b> returns the CHAR version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(CHAR)</code>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getuchar">ExtRemoteData::GetUchar</a>
 

 

