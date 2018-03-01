---
UID: NF:wiautil.wiauRegGetStrW
title: wiauRegGetStrW function
author: windows-driver-content
description: The wiauRegGetStr function gets a string value from the DeviceData section of the registry.
old-location: image\wiaureggetstr.htm
old-project: image
ms.assetid: ff06737b-c37d-4f37-adfc-bbd51974c9e4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaureggetstr, wiauFncs_b9145502-734d-40de-8086-c1f193966269.xml, wiauRegGetStr, wiauRegGetStr function [Imaging Devices], wiauRegGetStrA, wiauRegGetStrW, wiautil/wiauRegGetStr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiautil.h
api_name:
-	wiauRegGetStr
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauRegGetStrW function


## -description


The <b>wiauRegGetStr</b> function gets a string value from the <b>DeviceData</b> section of the registry.


## -syntax


````
HRESULT _stdcall wiauRegGetStr(
  _In_    HKEY   hkKey,
  _In_    PCTSTR pwszValueName,
  _Out_   PWSTR  pwszValue,
  _Inout_ DWORD  *pdwLength
);
````


## -parameters




### -param hkKey [in]

Specifies the registry key handle. This parameter should be set to the value pointed to by the <i>phkeyDeviceData </i>parameter when <a href="https://msdn.microsoft.com/library/windows/hardware/ff550179">wiauRegOpenData</a> returns.


#### - pwszValueName [in]

Points to the first character of a Unicode string containing the name of the registry entry.


#### - pwszValue [out]

Pointer to a memory location that receives the string value, including a terminating null character.


### -param pdwLength [in, out]

Pointer to a memory location that receives the length, in bytes, of the string value pointed to by the <i>pwszValue</i> parameter. The length includes the terminating null character.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550179">wiauRegOpenData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550176">wiauRegGetDword</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauRegGetStr function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

