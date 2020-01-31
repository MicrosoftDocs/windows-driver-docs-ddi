---
UID: NF:engextcpp.ExtRemoteData.GetW32Bool
title: ExtRemoteData::GetW32Bool (engextcpp.h)
description: The GetW32Bool method returns a BOOL version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getw32bool.htm
tech.root: debugger
ms.assetid: a17812f5-4e20-4793-9352-3cabed25a6da
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_367ee79b-5fdf-41ca-b43c-f9f29b3a872c.xml, ExtRemoteData class [Windows Debugging],GetW32Bool method, ExtRemoteData.GetW32Bool, ExtRemoteData::GetW32Bool, GetW32Bool, GetW32Bool method [Windows Debugging], GetW32Bool method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getw32bool
f1_keywords:
 - "engextcpp/ExtRemoteData.GetW32Bool"
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
- ExtRemoteData.GetW32Bool
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetW32Bool


## -description


The <b>GetW32Bool</b> method returns a BOOL version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -returns



<b>GetW32Bool</b> returns the BOOL version of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(BOOL)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOL is one of these types.  For the C++ <b>bool</b> type, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getstdbool">ExtRemoteData::GetStdBool</a>.  For the BOOLEAN type, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getboolean">ExtRemoteData::GetBoolean</a>.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getboolean">ExtRemoteData::GetBoolean</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getstdbool">ExtRemoteData::GetStdBool</a>
 

 

