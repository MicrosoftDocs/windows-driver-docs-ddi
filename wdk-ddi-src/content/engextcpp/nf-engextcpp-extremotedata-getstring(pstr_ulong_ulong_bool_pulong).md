---
UID: NF:engextcpp.ExtRemoteData.GetString(PSTR,ULONG,ULONG,bool,PULONG)
title: ExtRemoteData::GetString (engextcpp.h)
description: The GetString method reads a null-terminated string from the target's memory. The string is located in the beginning of the region represented by the ExtRemoteData object.
old-location: debugger\extremotedata_getstring.htm
tech.root: debugger
ms.assetid: ff0aa7a7-1efd-4d55-8865-f36c039b27a1
ms.date: 04/24/2018
keywords: ["ExtRemoteData::GetString"]
ms.keywords: EngExtCpp_Ref_0e8b8a7f-d6d4-4262-a1ed-5829a83ec80d.xml, ExtRemoteData class [Windows Debugging],GetString method, ExtRemoteData.GetString, ExtRemoteData::GetString, GetString, GetString method [Windows Debugging], GetString method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getstring
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
 - ExtRemoteData::GetString
 - engextcpp/ExtRemoteData::GetString
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - engextcpp.hpp
api_name:
 - ExtRemoteData.GetString
---

# ExtRemoteData::GetString


## -description

The <b>GetString</b> method reads a null-terminated string from the target's memory.  The string is located in the beginning of the region represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object.

## -parameters

### -param Buffer 

[out]
Receives the null-terminated string read from the target.  The type of <i>Buffer</i> must be the same as the type of the string on the target.  If the string is a Unicode string, the type of <i>Buffer</i> must be PWSTR.  If the string is a multibyte string, the type of <i>Buffer</i> must be PSTR.

<div class="alert"><b>Note</b>   the remainder of the <i>Buffer</i> buffer, after the string, can be overwritten by this method.</div>
<div> </div>

#### - BufferChars [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.

### -param MaxChars 

[in]
Specifies the maximum number of characters to read from the target.


#### - MustFit [in]

Specifies what happens if the string is larger than <i>BufferChars</i> characters.  If <i>MustFit</i> is <code>true</code> and the string is larger than <i>BufferChars</i> characters, an <b>ExtRemoteException</b> will be thrown.  If <i>MustFit</i> is <code>false</code> and the string is larger than <i>BufferChars</i> characters, the string will be truncated and null-terminated to fit inside the <i>Buffer</i> buffer.

### -param NeedChars

## -returns

<b>GetString</b> returns the null-terminated string that was read from the target.  This is <i>Buffer</i>.

## -remarks

This method can only be used if the region represented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a> object is in virtual memory.  It will not work if the region specifies physical memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-extremotedata(pcstr_ulong64_ulong)">ExtRemoteData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-extremotedata-readbuffer">ExtRemoteData::ReadBuffer</a>

