---
UID: NF:engextcpp.ExtRemoteData.WriteBuffer
title: ExtRemoteData::WriteBuffer (engextcpp.h)
description: The WriteBuffer method writes data to the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different.
old-location: debugger\extremotedata_writebuffer.htm
tech.root: debugger
ms.assetid: b50f0cf3-4cd5-4f9e-9749-49b1c9365a8f
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_0a08b058-ddc3-44e4-9d80-bb20d6e8f952.xml, ExtRemoteData class [Windows Debugging],WriteBuffer method, ExtRemoteData.WriteBuffer, ExtRemoteData::WriteBuffer, WriteBuffer, WriteBuffer method [Windows Debugging], WriteBuffer method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_writebuffer
ms.topic: method
f1_keywords:
 - "engextcpp/ExtRemoteData.WriteBuffer"
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
- ExtRemoteData.WriteBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::WriteBuffer


## -description


The <b>WriteBuffer</b> method writes data to the target's memory.  The data is located in the beginning of the region represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.  However, the size of the data can be different.


## -parameters




### -param Buffer [in]

Specifies the data to write to the target.


### -param Bytes [in]

Specifies the number of bytes to write.  The <i>Buffer</i> buffer must be at least this size.


### -param MustWriteAll






#### - MustReadAll [in]

Specifies what happens if the debugger engine is unable to write all the data to the target.  If <i>MustReadAll</i> is <code>true</code> and the debugger engine is unable to write <i>Bytes</i> bytes to the target, an <b>ExtRemoteException</b> will be thrown.  If <i>MustReadAll</i> is <code>false</code>, no exception will be thrown if the engine is unable to write the requested number of bytes to the target.


## -returns



<b>WriteBuffer</b> returns the number of bytes written to the target from the <i>Buffer</i> buffer.  If <i>MustReadAll</i> is <code>true</code>, the value of <i>Bytes</i> will be returned (unless an exception is thrown).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotedata-readbuffer">ExtRemoteData::ReadBuffer</a>
 

 

