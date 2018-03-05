---
UID: NF:ntifs.SeImpersonateClientEx
title: SeImpersonateClientEx function
author: windows-driver-content
description: The SeImpersonateClientEx routine causes a thread to impersonate a user.
old-location: ifsk\seimpersonateclientex.htm
old-project: ifsk
ms.assetid: 7a5043b9-2517-454a-a8d3-1ea09143c81a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SeImpersonateClientEx, SeImpersonateClientEx routine [Installable File System Drivers], ifsk.seimpersonateclientex, ntifs/SeImpersonateClientEx, seref_557d14bb-0d77-4bc8-8c75-57bb3c789963.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SeImpersonateClientEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SeImpersonateClientEx function


## -description


The <b>SeImpersonateClientEx</b> routine causes a thread to impersonate a user.


## -syntax


````
NTSTATUS SeImpersonateClientEx(
  _In_     PSECURITY_CLIENT_CONTEXT ClientContext,
  _In_opt_ PETHREAD                 ServerThread
);
````


## -parameters




### -param ClientContext [in]

Pointer to the user's security client context.


### -param ServerThread [in, optional]

Pointer to the thread that is to impersonate the user. If not specified, the calling thread is used.


## -returns



<b>SeImpersonateClientEx</b> returns an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The impersonation attempt succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The thread specified in <i>ServerThread</i> parameter did not have sufficient access rights to impersonate the user whose security client context is specified in the <i>ClientContext</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>SeImpersonateClientEx</b> encountered a pool allocation failure when allocating memory for the impersonation information structure.

</td>
</tr>
</table>
 




## -remarks



<b>SeImpersonateClientEx</b> is used to cause a thread to impersonate a user. The client security context in <i>ClientContext</i> is assumed to be up to date.

It is extremely unsafe to raise the privilege state of an untrusted user thread (take a user's thread and impersonate LocalSystem, for example). If an untrusted user thread had its privilege raised, the user could grab the thread token after it has been elevated and subvert the security of the entire system. 

In cases where a higher privilege state is required, the task should be dispatched to a work queue where the task can be safely handled by system worker thread. This way no impersonation is necessary.

To end the impersonation of the user, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556717">SeStopImpersonatingClient</a> routine.

The <a href="..\ntifs\nf-ntifs-psimpersonateclient.md">PsImpersonateClient</a> routine can be used to cause a server thread to impersonate a client.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-psimpersonateclient.md">PsImpersonateClient</a>



<a href="..\ntifs\nf-ntifs-secreateclientsecurityfromsubjectcontext.md">SeCreateClientSecurityFromSubjectContext</a>



<a href="..\ntifs\nf-ntifs-secreateclientsecurity.md">SeCreateClientSecurity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556717">SeStopImpersonatingClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeImpersonateClientEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

