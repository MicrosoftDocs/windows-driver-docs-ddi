---
UID: NF:wdm.IoIsWdmVersionAvailable
title: IoIsWdmVersionAvailable function
author: windows-driver-content
description: The IoIsWdmVersionAvailable routine checks whether a given WDM version is supported by the operating system.
old-location: kernel\ioiswdmversionavailable.htm
old-project: kernel
ms.assetid: 80b72de0-02a6-4891-b74a-c41cb14fa629
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.ioiswdmversionavailable, k104_775d6afa-6edd-4922-bdff-a8fe5d32bc3a.xml, IoIsWdmVersionAvailable routine [Kernel-Mode Driver Architecture], wdm/IoIsWdmVersionAvailable, IoIsWdmVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoIsWdmVersionAvailable
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoIsWdmVersionAvailable function


## -description


The <b>IoIsWdmVersionAvailable</b> routine checks whether a given WDM version is supported by the operating system.


## -syntax


````
BOOLEAN IoIsWdmVersionAvailable(
  _In_ UCHAR MajorVersion,
  _In_ UCHAR MinorVersion
);
````


## -parameters




### -param MajorVersion [in]

Specifies the major version number of WDM that is requested.


### -param MinorVersion [in]

Specifies the minor version number of WDM that is requested.


## -returns



<b>IoIsWdmVersionAvailable</b> returns <b>TRUE</b> if the version of WDM that the operating system provides is greater than or equal to the version number of WDM being requested. Otherwise, it returns <b>FALSE</b>.




## -remarks



Drivers should use the <a href="..\wdm\nf-wdm-rtlisntddiversionavailable.md">RtlIsNtDdiVersionAvailable</a> routine instead of the <b>IoIsWdmVersionAvailable</b> routine.

Cross-platform drivers should use this routine to check the WDM version before performing any operations that vary by platform or are not supported in all versions of WDM.

The WDM_MAJORVERSION and WDM_MINORVERSION constants, which are defined in the Wdm.h header file, specify the WDM major and minor version numbers for the current version of Windows. The following lists the WDM version provided with each operating system.

<table>
<tr>
<th>Operating system</th>
<th>WDM major version</th>
<th>WDM minor version</th>
</tr>
<tr>
<td>
Windows 7

</td>
<td>
6

</td>
<td>
0x00

</td>
</tr>
<tr>
<td>
Windows Server 2008 R2

</td>
<td>
6

</td>
<td>
0x00

</td>
</tr>
<tr>
<td>
Windows Server 2008

</td>
<td>
6

</td>
<td>
0x00

</td>
</tr>
<tr>
<td>
Windows Vista

</td>
<td>
6

</td>
<td>
0x00

</td>
</tr>
<tr>
<td>
Windows Server 2003

</td>
<td>
1

</td>
<td>
0x30

</td>
</tr>
<tr>
<td>
Windows XP

</td>
<td>
1

</td>
<td>
0x20

</td>
</tr>
<tr>
<td>
Windows 2000

</td>
<td>
1

</td>
<td>
0x10

</td>
</tr>
<tr>
<td>
Windows Me

</td>
<td>
1

</td>
<td>
0x05

</td>
</tr>
<tr>
<td>
Windows 98

</td>
<td>
1

</td>
<td>
0x00

</td>
</tr>
</table>
 

Note that the minor version number is defined as a hexadecimal value.

Later versions of WDM support all the features available in earlier versions of WDM; that is, each version of WDM is a superset of the previous WDM version.

The following call returns <b>TRUE</b> on any of the listed operating systems, because all these systems support all the features of WDM 1.0:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>bVersion = IoIsWdmVersionAvailable(1,0);</pre>
</td>
</tr>
</table></span></div>
The following example shows how a driver can dynamically detect the current operating system:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (IoIsWdmVersionAvailable(1, 0x10)) {
    //
    //If WDM 1.10 is supported, this is Windows 2000
    //or better.
    //
} else if (IoIsWdmVersionAvailable(1, 5)) {
    //
    //If WDM 1.05 is supported, this is Windows ME
    //or better.
    //
} else {
    //
    //WDM 1.0 is always supported, so this is Windows 98, 
    //Windows 98 SE, or better.
    //
}</pre>
</td>
</tr>
</table></span></div>
As the example shows, calling <b>IoIsWdmVersionAvailable</b>(1, 5) returns <b>TRUE</b> on Windows Me, Windows 2000, and any succeeding operating systems, but <b>FALSE</b> on Windows 98 and Windows 98 SE.




## -see-also

<a href="..\wdm\nf-wdm-rtlisntddiversionavailable.md">RtlIsNtDdiVersionAvailable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoIsWdmVersionAvailable routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

