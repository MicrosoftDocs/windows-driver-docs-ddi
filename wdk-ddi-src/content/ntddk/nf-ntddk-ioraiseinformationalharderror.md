---
UID: NF:ntddk.IoRaiseInformationalHardError
title: IoRaiseInformationalHardError function
author: windows-driver-content
description: The IoRaiseInformationalHardError routine sends a dialog box to the user, warning about a device I/O error that indicates why a user I/O request failed.
old-location: kernel\ioraiseinformationalharderror.htm
old-project: kernel
ms.assetid: 14e9a28c-65cc-4e90-8220-85f1981c8cd7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRaiseInformationalHardError, IoRaiseInformationalHardError routine [Kernel-Mode Driver Architecture], kernel.ioraiseinformationalharderror, k104_7af16dc2-0500-411e-962a-7d8c1fe40ba0.xml, ntddk/IoRaiseInformationalHardError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoRaiseInformationalHardError
product: Windows
targetos: Windows
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# IoRaiseInformationalHardError function


## -description


The <b>IoRaiseInformationalHardError</b> routine sends a dialog box to the user, warning about a device I/O error that indicates why a user I/O request failed.


## -syntax


````
BOOLEAN IoRaiseInformationalHardError(
  _In_     NTSTATUS        ErrorStatus,
  _In_opt_ PUNICODE_STRING String,
  _In_opt_ PKTHREAD        Thread
);
````


## -parameters




### -param ErrorStatus [in]

The error status code (IO_ERR_<i>XXX</i>). 


### -param String [in, optional]

A pointer to a Unicode string, which provides additional information about the error. Some NT status codes require a string parameter, such as a file or directory name. If the specified <i>ErrorStatus</i> value does not require a string parameter, set <i>String</i> to <b>NULL</b>.


### -param Thread [in, optional]

A pointer to the thread whose IRP was failed due to the error specified by the <i>ErrorStatus</i> parameter.


## -returns


<b>IoRaiseInformationalHardError</b> returns <b>TRUE</b> if the dialog box was successfully queued. This routine returns <b>FALSE</b> if dialog boxes are disabled for <i>Thread</i>, a pool allocation failed, too many dialog boxes are already queued, or an equivalent dialog box is already pending a user response (such as waiting for the user to press RETURN).



## -remarks


<b>IoRaiseInformationalHardError</b> takes a system-defined NT error value as a parameter. Driver writers can use the event log APIs to communicate driver-defined event strings to the user.

<b>IoRaiseInformationalHardError</b> behaves as follows:
<ul>
<li>If the caller-supplied <i>ErrorStatus</i> value is not defined in the Ntstatus.h header file, the dialog box always shows the text "Unknown Hard Error", regardless of the <i>String</i> parameter value.</li>
<li>If the caller-supplied <i>ErrorStatus</i> value is defined in the Ntstatus.h header file, the dialog box shows the text in the corresponding MessageText string in Ntstatus.h, regardless of the <i>String</i> parameter value.</li>
<li>If the <i>Thread</i> parameter specifies a thread that is running in the context of an application, the text shown in the dialog box is "ApplicationName.exe - System Error".</li>
<li>If the <i>Thread</i> parameter is NULL or if it specifies a thread that is running in an arbitrary system context, the text shown in the dialog box is "System Process - System Error". Additionally, if the <i>ErrorStatus</i> value is defined in Ntstatus.h, the corresponding MessageText string is written to the event log.</li>
</ul>If a previous call to the <a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a> routine disabled hard errors for the specified thread, <b>IoRaiseInformationalHardError</b> returns <b>FALSE</b>.

Starting with Windows Vista, if the routine is called from a thread in session 0 (that is, from any system thread), no dialog box appears when the routine succeeds and returns <b>TRUE</b>.



## -see-also

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>

<a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a>

<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRaiseInformationalHardError routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

