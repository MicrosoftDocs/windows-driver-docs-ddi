---
UID: NF:engextcpp.ExtRemoteData.GetString
title: ExtRemoteData::GetString method
author: windows-driver-content
description: The GetString method reads a null-terminated string from the target's memory. The string is located in the beginning of the region represented by the ExtRemoteData object.
old-location: debugger\extremotedata_getstring.htm
old-project: debugger
ms.assetid: ff0aa7a7-1efd-4d55-8865-f36c039b27a1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ExtRemoteData class [Windows Debugging], GetString method, EngExtCpp_Ref_0e8b8a7f-d6d4-4262-a1ed-5829a83ec80d.xml, ExtRemoteData, GetString, ExtRemoteData::GetString, GetString method [Windows Debugging], GetString method [Windows Debugging], ExtRemoteData class, debugger.extremotedata_getstring
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteData.GetString
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetString method


## -description


The <b>GetString</b> method reads a null-terminated string from the target's memory.  The string is located in the beginning of the region represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.


## -syntax


````
PTSTR GetString(
  [out] PTSTR Buffer,
  [in]  ULONG BufferChars,
  [in]  ULONG MaxChars,
  [in]  bool  MustFit
);
````


## -parameters




### -param Buffer [out]

Receives the null-terminated string read from the target.  The type of <i>Buffer</i> must be the same as the type of the string on the target.  If the string is a Unicode string, the type of <i>Buffer</i> must be PWSTR.  If the string is a multibyte string, the type of <i>Buffer</i> must be PSTR.

<div class="alert"><b>Note</b>   the remainder of the <i>Buffer</i> buffer, after the string, can be overwritten by this method.</div>
<div> </div>

### -param BufferChars [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param MaxChars [in]

Specifies the maximum number of characters to read from the target.


### -param MustFit [in]

Specifies what happens if the string is larger than <i>BufferChars</i> characters.  If <i>MustFit</i> is <code>true</code> and the string is larger than <i>BufferChars</i> characters, an <b>ExtRemoteException</b> will be thrown.  If <i>MustFit</i> is <code>false</code> and the string is larger than <i>BufferChars</i> characters, the string will be truncated and null-terminated to fit inside the <i>Buffer</i> buffer.


### -param NeedChars






## -returns



<b>GetString</b> returns the null-terminated string that was read from the target.  This is <i>Buffer</i>.




## -remarks



This method can only be used if the region represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object is in virtual memory.  It will not work if the region specifies physical memory.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544088">ExtRemoteData::ReadBuffer</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetString method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

