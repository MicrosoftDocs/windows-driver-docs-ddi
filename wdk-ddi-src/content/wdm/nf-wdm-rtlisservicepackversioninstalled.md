---
UID: NF:wdm.RtlIsServicePackVersionInstalled
title: RtlIsServicePackVersionInstalled function
author: windows-driver-content
description: The RtlIsServicePackVersionInstalled routine determines if a specified service pack version of the Microsoft Windows device driver interface (DDI) is installed.
old-location: kernel\rtlisservicepackversioninstalled.htm
old-project: kernel
ms.assetid: 1314ffb5-e6e2-4c22-bc67-388da3bcbe79
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlisservicepackversioninstalled, RtlIsServicePackVersionInstalled, RtlIsServicePackVersionInstalled routine [Kernel-Mode Driver Architecture], wdm/RtlIsServicePackVersionInstalled, k109_1552acd9-7036-45d2-bd1c-57b7a2154ecb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows. A compatibility library supports this routine in earlier versions of Windows (see Remarks section).
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
req.lib: Rtlver.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Rtlver.lib
-	Rtlver.dll
apiname: 
-	RtlIsServicePackVersionInstalled
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIsServicePackVersionInstalled function


## -description


The <b>RtlIsServicePackVersionInstalled</b> routine determines if a specified service pack version of the Microsoft Windows device driver interface (DDI) is installed.


## -syntax


````
BOOLEAN RtlIsServicePackVersionInstalled(
  _In_ ULONG Version
);
````


## -parameters




### -param Version [in]

The service pack version of the Windows DDI that is available. The following table lists the possible values for <i>Version</i>.
<table>
<tr>
<th>Constant</th>
<th>Windows version</th>
</tr>
<tr>
<td>
NTDDI_WIN7

</td>
<td>
Windows 7 and Windows Server 2008 R2

</td>
</tr>
<tr>
<td>
NTDDI_WS08SP2

</td>
<td>
Windows Server 2008 with Service Pack 2 (SP2)

</td>
</tr>
<tr>
<td>
NTDDI_WS08

</td>
<td>
Windows Server 2008

</td>
</tr>
<tr>
<td>
NTDDI_VISTASP2

</td>
<td>
Windows Vista with SP2

</td>
</tr>
<tr>
<td>
NTDDI_VISTASP1

</td>
<td>
Windows Vista with SP1

</td>
</tr>
<tr>
<td>
NTDDI_VISTA

</td>
<td>
Windows Vista

</td>
</tr>
<tr>
<td>
NTDDI_WS03SP2

</td>
<td>
Windows Server 2003 with SP2

</td>
</tr>
<tr>
<td>
NTDDI_WS03SP1

</td>
<td>
Windows Server 2003 with SP1

</td>
</tr>
<tr>
<td>
NTDDI_WS03

</td>
<td>
Windows Server 2003

</td>
</tr>
<tr>
<td>
NTDDI_WINXPSP3

</td>
<td>
Windows XP with SP3

</td>
</tr>
<tr>
<td>
NTDDI_WINXPSP2

</td>
<td>
Windows XP with SP2

</td>
</tr>
<tr>
<td>
NTDDI_WINXPSP1

</td>
<td>
Windows XP with SP1

</td>
</tr>
<tr>
<td>
NTDDI_WINXP

</td>
<td>
Windows XP

</td>
</tr>
<tr>
<td>
NTDDI_WIN2KSP4

</td>
<td>
Windows 2000 with SP4

</td>
</tr>
<tr>
<td>
NTDDI_WIN2KSP3

</td>
<td>
Windows 2000 with SP3

</td>
</tr>
<tr>
<td>
NTDDI_WIN2KSP2

</td>
<td>
Windows 2000 with SP2

</td>
</tr>
<tr>
<td>
NTDDI_WIN2KSP1

</td>
<td>
Windows 2000 with SP1

</td>
</tr>
<tr>
<td>
NTDDI_WIN2K

</td>
<td>
Windows 2000

</td>
</tr>
</table> 

The NTDDI_<i>XXX</i> constants are defined in the Sdkddkver.h header file. The preceding table does not contain an entry for Windows Server 2008 with SP1. The first service pack to become available for Windows Server 2008 is SP2. 


## -returns


<b>RtlIsServicePackVersionInstalled</b> returns <b>TRUE</b> if the service pack version of the Windows operating system that is running is the same or later than the version that the <i>Version</i> parameter specifies. Otherwise, this routine returns <b>FALSE</b>. <b>RtlIsServicePackVersionInstalled</b> also returns <b>FALSE</b> if the major version (for example, Windows Vista or Windows Server 2003) that <i>Version</i> specifies does not match the major version of Windows that is currently running on the computer.



## -remarks


The <b>RtlIsServicePackVersionInstalled</b> routine compares the version that the <i>Version</i> parameter specifies to the version of the currently running Windows operating system.

Use the <a href="..\wdm\nf-wdm-rtlisntddiversionavailable.md">RtlIsNtDdiVersionAvailable</a> routine to determine if a major version of Windows is running.

For more information about <b>RtlIsServicePackVersionInstalled</b> and <b>RtlIsNtDdiVersionAvailable</b>, see <a href="https://msdn.microsoft.com/7d02148d-502d-4b49-9c56-9fff498dd2af">Header File Changes in the Windows Driver Kit</a>.

The Windows kernel implements <b>RtlIsServicePackVersionInstalled</b> only in Windows Vista and later versions of Windows. However, a compatibility library, Rtlver.lib, implements a version of <b>RtlIsServicePackVersionInstalled</b> that runs in Windows 2000 and later versions of Windows. For kernel-mode drivers that include the Wdm.h header file, calls to <b>RtlIsServicePackVersionInstalled</b> go to the version of this routine that is implemented in Rtlver.lib.



## -see-also

<a href="..\wdm\nf-wdm-rtlverifyversioninfo.md">RtlVerifyVersionInfo</a>

<a href="..\wdm\nf-wdm-rtlisntddiversionavailable.md">RtlIsNtDdiVersionAvailable</a>

<a href="..\wdm\nf-wdm-psgetversion.md">PsGetVersion</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIsServicePackVersionInstalled routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

