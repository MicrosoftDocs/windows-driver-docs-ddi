---
UID: NF:engextcpp.ExtRemoteData.ExtRemoteData
title: ExtRemoteData::ExtRemoteData (engextcpp.h)
description: The ExtRemoteData constructor creates a new instance of the ExtRemoteData class.
old-location: debugger\extremotedata_extremotedata.htm
tech.root: debugger
ms.assetid: c463169e-5e18-44bb-b954-8a99d24edd0c
ms.date: 08/09/2018
keywords: ["ExtRemoteData::ExtRemoteData"]
ms.keywords: EngExtCpp_Ref_8e376094-9e23-4ea4-81e3-c47e6695a687.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging],ExtRemoteData constructor, ExtRemoteData constructor [Windows Debugging], ExtRemoteData constructor [Windows Debugging],ExtRemoteData class, ExtRemoteData.ExtRemoteData, ExtRemoteData.ExtRemoteData(), ExtRemoteData::ExtRemoteData, debugger.extremotedata_extremotedata
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
 - ExtRemoteData::ExtRemoteData
 - engextcpp/ExtRemoteData::ExtRemoteData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.ExtRemoteData
---

# ExtRemoteData::ExtRemoteData


## -description

The <b>ExtRemoteData</b> constructor creates a new instance of the [ExtRemoteData](nl-engextcpp-extremotedata.md) class.

## -remarks

If a memory region is specified, the contents of the region are read from the target and cached.  The data can be retrieved using [ExtRemoteData::GetData](nf-engextcpp-extremotedata-getdata.md).

The constructor is called by the ExtRemoteData::Set(Typed) or ExtRemoteData::Set(Offset Bytes) methods and the ExtRemoteData::GetData method.

## -see-also

[ExtRemoteData](nl-engextcpp-extremotedata.md)

[ExtRemoteData::GetData](nf-engextcpp-extremotedata-getdata.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData::ExtRemoteData (Name, Offset, Bytes)</a>

