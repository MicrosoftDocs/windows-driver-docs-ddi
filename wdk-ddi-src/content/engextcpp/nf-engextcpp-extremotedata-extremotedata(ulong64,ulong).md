---
UID: NF:engextcpp.ExtRemoteData.ExtRemoteData(ULONG64,ULONG)
title: ExtRemoteData::ExtRemoteData(ULONG64,ULONG) (engextcpp.h)
description: The ExtRemoteData constructor creates a new instance of the ExtRemoteData class.
old-location: debugger\extremotedata_extremotedata_offset_bytes.htm
tech.root: debugger
ms.assetid: 0785b24d-e2f3-45f2-9b05-f2f477ad3d99
ms.date: 08/09/2018
keywords: ["ExtRemoteData::ExtRemoteData(ULONG64,ULONG)"]
ms.keywords: ExtRemoteData, ExtRemoteData class [Windows Debugging],ExtRemoteData constructor, ExtRemoteData constructor [Windows Debugging], ExtRemoteData constructor [Windows Debugging],ExtRemoteData class, ExtRemoteData.ExtRemoteData, ExtRemoteData.ExtRemoteData(ULONG64,ULONG), ExtRemoteData::ExtRemoteData, ExtRemoteData::ExtRemoteData(ULONG64,ULONG), debugger.extremotedata_extremotedata_offset_bytes
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
ms.custom: RS5
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

# ExtRemoteData::ExtRemoteData(ULONG64,ULONG)


## -description

The <b>ExtRemoteData</b> constructor creates a new instance of the[ExtRemoteData](nl-engextcpp-extremotedata.md) class.

## -parameters

### -param Offset 

[in]Location of the beginning of the memory region in the target's virtual address space.

### -param Bytes 

[in]Number of bytes in the memory region.

## -remarks

If a memory region is specified, the contents of the region are read from the target and cached.  The data can be retrieved using [ExtRemoteData::GetData](nf-engextcpp-extremotedata-getdata.md) or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.

The constructor is called by the ExtRemoteData::Set(Typed), ExtRemoteData::Set(Offset Bytes) methods and the ExtRemoteData::GetData method.

## -see-also

[ExtRemoteData](nl-engextcpp-extremotedata.md)

[ExtRemoteData::GetData](nf-engextcpp-extremotedata-getdata.md) 

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData::ExtRemoteData (Name, Offset, Bytes)</a>

