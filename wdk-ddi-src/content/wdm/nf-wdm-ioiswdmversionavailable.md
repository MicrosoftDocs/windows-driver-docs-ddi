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
ms.keywords: IoIsWdmVersionAvailable
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
req.alt-api: IoIsWdmVersionAvailable
req.alt-loc: NtosKrnl.exe
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

Windows 7

6

0x00

Windows Server 2008 R2

Windows Server 2008

Windows Vista

Windows Server 2003

1

0x30

Windows XP

0x20

Windows 2000

0x10

Windows Me

0x05

Windows 98

Note that the minor version number is defined as a hexadecimal value.

Later versions of WDM support all the features available in earlier versions of WDM; that is, each version of WDM is a superset of the previous WDM version.

The following call returns <b>TRUE</b> on any of the listed operating systems, because all these systems support all the features of WDM 1.0:

The following example shows how a driver can dynamically detect the current operating system:

As the example shows, calling <b>IoIsWdmVersionAvailable</b>(1, 5) returns <b>TRUE</b> on Windows Me, Windows 2000, and any succeeding operating systems, but <b>FALSE</b> on Windows 98 and Windows 98 SE.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlisntddiversionavailable.md">RtlIsNtDdiVersionAvailable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoIsWdmVersionAvailable routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

