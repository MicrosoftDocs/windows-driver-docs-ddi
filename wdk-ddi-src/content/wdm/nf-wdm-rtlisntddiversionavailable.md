---
UID: NF:wdm.RtlIsNtDdiVersionAvailable
title: RtlIsNtDdiVersionAvailable function
author: windows-driver-content
description: The RtlIsNtDdiVersionAvailable routine determines if a specified version of the Microsoft Windows device driver interface (DDI) is available.
old-location: kernel\rtlisntddiversionavailable.htm
old-project: kernel
ms.assetid: 54017f67-b01f-48bd-a5bb-598902672c4f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlisntddiversionavailable, k109_62b3efdd-6678-4e88-92cb-eaacff80bfab.xml, RtlIsNtDdiVersionAvailable routine [Kernel-Mode Driver Architecture], RtlIsNtDdiVersionAvailable, wdm/RtlIsNtDdiVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista. A compatibility library supports this routine in earlier versions of Windows (see Remarks section).
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
-	RtlIsNtDdiVersionAvailable
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlIsNtDdiVersionAvailable function


## -description


The <b>RtlIsNtDdiVersionAvailable</b> routine determines if a specified version of the Microsoft Windows device driver interface (DDI) is available.


## -syntax


````
BOOLEAN RtlIsNtDdiVersionAvailable(
  _In_ ULONG Version
);
````


## -parameters




### -param Version [in]

The version of the Windows DDI that is available. The following table lists the possible values for the <i>Version</i> parameter.
<table>
<tr>
<th>Constant</th>
<th>Windows version</th>
</tr>
<tr>
<td>
NTDDI_WINBLUE

</td>
<td>
Windows 8.1

</td>
</tr>
<tr>
<td>
NTDDI_WIN8

</td>
<td>
Windows 8

</td>
</tr>
<tr>
<td>
NTDDI_WIN7

</td>
<td>
Windows 7

</td>
</tr>
<tr>
<td>
NTDDI_WS08

</td>
<td>
Windows Server 2008

</td>
</tr>
<tr>
<td>
NTDDI_VISTA

</td>
<td>
Windows Vista

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
NTDDI_WINXP

</td>
<td>
Windows XP

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

The NTDDI_<i>XXX</i> constants are defined in the Sdkddkver.h header file.

Additional NTDDI_<i>XXX</i> constants that specify service packs are available for the <a href="..\wdm\nf-wdm-rtlisservicepackversioninstalled.md">RtlIsServicePackVersionInstalled</a> routine. Do not use these values for <b>RtlIsNtDdiVersionAvailable</b>. 


## -returns


<b>RtlIsNtDdiVersionAvailable</b> returns <b>TRUE</b> if the version of the Windows operating system that is running is the same or later than the version that the <i>Version</i> parameter specifies. Otherwise, this routine returns <b>FALSE</b>. 



## -remarks


The <b>RtlIsNtDdiVersionAvailable</b> routine compares the version that the <i>Version</i> parameter specifies to the version of the Windows operating system that is currently running.

Use the <a href="..\wdm\nf-wdm-rtlisservicepackversioninstalled.md">RtlIsServicePackVersionInstalled</a> routine if you want to determine whether a particular service pack is installed.

The Windows kernel implements <b>RtlIsNtDdiVersionAvailable</b> only in Windows Vista and later versions of Windows. However, a compatibility library, Rtlver.lib, implements a version of <b>RtlIsNtDdiVersionAvailable</b> that runs in Windows 2000 and later versions of Windows. For kernel-mode drivers that include the Wdm.h header file, calls to <b>RtlIsNtDdiVersionAvailable</b> go to the version of this routine that is implemented in Rtlver.lib.

For more information about <b>RtlIsNtDdiVersionAvailable</b> and <b>RtlIsServicePackVersionInstalled</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554887">Writing Drivers for Different Versions of Windows</a>.



## -see-also

<a href="..\wdm\nf-wdm-rtlisservicepackversioninstalled.md">RtlIsServicePackVersionInstalled</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlIsNtDdiVersionAvailable routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

