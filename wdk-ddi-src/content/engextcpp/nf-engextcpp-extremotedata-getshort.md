---
UID: NF:engextcpp.ExtRemoteData.GetShort
title: ExtRemoteData::GetShort (engextcpp.h)
description: The GetShort method returns a SHORT version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getshort.htm
tech.root: debugger
ms.assetid: 5e364e83-76db-44b0-b5bc-15eed53bbbdf
ms.date: 05/03/2018
keywords: ["ExtRemoteData::GetShort"]
ms.keywords: EngExtCpp_Ref_c2fffdd2-e899-4f87-bd00-415bafa3b84f.xml, ExtRemoteData class [Windows Debugging],GetShort method, ExtRemoteData.GetShort, ExtRemoteData::GetShort, GetShort, GetShort method [Windows Debugging], GetShort method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getshort
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
 - ExtRemoteData::GetShort
 - engextcpp/ExtRemoteData::GetShort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetShort
---

# ExtRemoteData::GetShort


## -description

The <b>GetShort</b> method returns a SHORT version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object, which represents the contents of the target's memory.

## -returns

<b>GetShort</b> returns the SHORT version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -remarks

The size of the memory represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object must be <code>sizeof(SHORT)</code>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getdata">ExtRemoteData::GetData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-getushort">ExtRemoteData::GetUshort</a>

