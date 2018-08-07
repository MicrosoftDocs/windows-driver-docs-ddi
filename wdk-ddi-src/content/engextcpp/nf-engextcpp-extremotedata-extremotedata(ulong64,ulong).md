---
UID: NF:engextcpp.ExtRemoteData.ExtRemoteData(ULONG64,ULONG)
title: ExtRemoteData::ExtRemoteData(ULONG64,ULONG)
author: windows-driver-content
description: The ExtRemoteData constructor creates a new instance of the ExtRemoteData class.
old-location: debugger\extremotedata_extremotedata_offset_bytes.htm
tech.root: debugger
ms.assetid: 0785b24d-e2f3-45f2-9b05-f2f477ad3d99
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: ExtRemoteData, ExtRemoteData class [Windows Debugging],ExtRemoteData constructor, ExtRemoteData constructor [Windows Debugging], ExtRemoteData constructor [Windows Debugging],ExtRemoteData class, ExtRemoteData.ExtRemoteData, ExtRemoteData.ExtRemoteData(ULONG64,ULONG), ExtRemoteData::ExtRemoteData, ExtRemoteData::ExtRemoteData(ULONG64,ULONG), debugger.extremotedata_extremotedata_offset_bytes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteData.ExtRemoteData
product:
-	Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::ExtRemoteData(ULONG64,ULONG)


## -description


The <b>ExtRemoteData</b> constructor creates a new instance of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> class.


## -parameters




### -param Offset [in]

Location of the beginning of the memory region in the target's virtual address space.


### -param Bytes [in]

Number of bytes in the memory region.


## -remarks



If a memory region is specified, the contents of the region are read from the target and cached.  The data can be retrieved using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.

The constructor is called by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>



<a href="https://msdn.microsoft.com/0728f32e-750a-4212-9b8d-f4bfe85978cb">ExtRemoteData::ExtRemoteData (Name, Offset, Bytes)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>
 

 

