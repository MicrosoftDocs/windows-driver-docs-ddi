---
UID: NF:storport.StorPortInitializeSpinlock
title: StorPortInitializeSpinlock function
author: windows-driver-content
description: The StorPortInitializeSpinLock routine initializes a variable of type STOR_KSPIN_LOCK.
old-location: storage\storportinitializespinlock.htm
old-project: storage
ms.assetid: 150B1ED3-572A-4986-BED6-628ED6C54CCF
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortInitializeSpinlock, storport/StorPortInitializeSpinlock, storage.storportinitializespinlock, StorPortInitializeSpinlock routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortInitializeSpinlock
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortInitializeSpinlock function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInitializeSpinLock </b>routine initializes a variable of type <b>STOR_KSPIN_LOCK</b>.


## -syntax


````
ULONG StorPortInitializeSpinlock(
  _In_  PVOID            HwDeviceExtension,
  _Out_ PSTOR_KSPIN_LOCK Lock
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Lock [out]

Pointer to a spin lock of type <b>STOR_KSPIN_LOCK</b>, for which the caller must provide the storage


## -returns


<b>StorPortInitializeSpinlock</b> returns one of the following status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list items were removed successfully or the list is already empty.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer in <i>ListHead</i> or <i>Result</i> is <b>NULL</b>.

</td>
</tr>
</table> 



## -remarks


This routine must be called before an initial call to <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>, to any other support routine that requires a spin lock as an argument.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567494">StorPortReleaseMSISpinLock</a>

<a href="..\storport\nf-storport-storportacquiremsispinlock.md">StorPortAcquireMSISpinLock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>

<a href="..\storport\nf-storport-storportreleasespinlock.md">StorPortReleaseSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeSpinlock routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

