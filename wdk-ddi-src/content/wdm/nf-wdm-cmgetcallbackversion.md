---
UID: NF:wdm.CmGetCallbackVersion
title: CmGetCallbackVersion function
author: windows-driver-content
description: The CmGetCallbackVersion routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature.
old-location: kernel\cmgetcallbackversion.htm
old-project: kernel
ms.assetid: 4b7aba14-bc6a-4d3d-bcc5-53fd122794a1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CmGetCallbackVersion, CmGetCallbackVersion routine [Kernel-Mode Driver Architecture], ConfigMgrRef_f15e2e9c-8b84-40b2-abb4-b37a6d38f920.xml, kernel.cmgetcallbackversion, wdm/CmGetCallbackVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CmGetCallbackVersion
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# CmGetCallbackVersion function


## -description


The <b>CmGetCallbackVersion</b> routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature.


## -syntax


````
VOID CmGetCallbackVersion(
  _Out_opt_ PULONG Major,
  _Out_opt_ PULONG Minor
);
````


## -parameters




### -param Major [out, optional]

A pointer to a location that receives the major version number.


### -param Minor [out, optional]

A pointer to a location that receives the minor version number.


## -returns



None




## -remarks



The <b>CmGetCallbackVersion</b> routine is available starting with Windows Vista.

For Windows Vista, the major version number is 1 and the minor version number is 0.

Starting with Windows 7, the major version number is 1 and the minor version number is 1.

Version 1.1 contains two changes from version 1.0.

First, in version 1.0, if multiple registry filter drivers are active on the computer at the same time, the <b>REG_POST_<i>XXX</i>_KEY_INFORMATION</b> structure passed to a driver's registry callback routine during the post-notification phase for a create-key or open-key operation might contain a non-NULL <b>Object</b> member, even though the operation failed and the <b>Status</b> member contains an error status. In version 1.1, the <b>Object</b> member is always NULL if the <b>Status</b> member is set to an error status value to indicate that the operation failed.

Second, in version 1.0, an uncaught exception in a registry callback routine is quietly accepted by the operating system. In version 1.1, this exception causes the computer to bug check.

For more information on the differences between versions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.




## -see-also

<a href="..\wdm\ns-wdm-_reg_post_create_key_information.md">REG_POST_CREATE_KEY_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560967">REG_POST_OPEN_KEY_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmGetCallbackVersion routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

