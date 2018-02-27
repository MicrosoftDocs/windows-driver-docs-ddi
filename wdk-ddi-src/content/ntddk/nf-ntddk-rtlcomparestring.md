---
UID: NF:ntddk.RtlCompareString
title: RtlCompareString function
author: windows-driver-content
description: The RtlCompareString routine compares two counted strings.
old-location: kernel\rtlcomparestring.htm
old-project: kernel
ms.assetid: 59d023d4-a2b4-4183-9572-cb48621c76fb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlCompareString, RtlCompareString routine [Kernel-Mode Driver Architecture], k109_a794007b-a40a-4081-8302-f7426c4ceaef.xml, kernel.rtlcomparestring, ntddk/RtlCompareString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlCompareString
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlCompareString function


## -description


The <b>RtlCompareString</b> routine compares two counted strings. 


## -syntax


````
LONG RtlCompareString(
  _In_ const STRING  *String1,
  _In_ const STRING  *String2,
  _In_       BOOLEAN CaseInSensitive
);
````


## -parameters




### -param String1 [in]

Pointer to the first string.


### -param String2 [in]

Pointer to the second string.


### -param CaseInSensitive [in]

If <b>TRUE</b>, case should be ignored when doing the comparison.


## -returns



<b>RtlCompareString</b> returns a signed value that gives the results of the comparison:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> equals <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>&lt; Zero</b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is less than <i>String2</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>&gt; Zero </b></dt>
</dl>
</td>
<td width="60%">
<i>String1</i> is greater than <i>String2</i>.

</td>
</tr>
</table>
 




## -see-also

<a href="..\ntddk\nf-ntddk-rtlequalstring.md">RtlEqualString</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlcompareunicodestring.md">RtlCompareUnicodeString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCompareString routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

