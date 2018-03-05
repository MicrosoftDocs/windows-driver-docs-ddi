---
UID: NF:storport.StorPortReleaseMSISpinLock
title: StorPortReleaseMSISpinLock function
author: windows-driver-content
description: The StorPortReleaseMSISpinLock routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message.
old-location: storage\storportreleasemsispinlock.htm
old-project: storage
ms.assetid: 5a2cf757-9dca-4717-a775-834a22c02a12
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReleaseMSISpinLock, StorPortReleaseMSISpinLock routine [Storage Devices], storage.storportreleasemsispinlock, storport/StorPortReleaseMSISpinLock, storprt_212b8090-c4a3-4ea8-8c50-6704a6d0cee7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortReleaseMSISpinLock
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReleaseMSISpinLock function


## -description


The <b>StorPortReleaseMSISpinLock</b> routine releases a previously acquired message signaled interrupt (MSI) spin lock for the specified message. 


## -syntax


````
ULONG StorPortReleaseMSISpinLock(
  _In_ PVOID HwDeviceExtension,
  _In_ ULONG MessageID,
  _In_ ULONG OldIrql
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MessageId

TBD


### -param OldIrql [in]

The IRQL that the <a href="..\storport\nf-storport-storportacquiremsispinlock.md">StorPortAcquireMSISpinLock</a> routine returned when the miniport driver acquired the spin lock.


#### - MessageID [in]

The identifier of the message.


## -returns



StorPortReleaseMSISpinLock returns one of the following status codes:

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
Indicates that the spin lock was released successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
HwDeviceExtension was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



Miniport drivers are not required to acquire MSI spin locks for messages unless the <b>InterruptSynchronizePerMessage</b> member of the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure indicates a synchronization mode of <b>InterruptSynchronizationMode</b>.




## -see-also

<a href="..\storport\nf-storport-storportacquiremsispinlock.md">StorPortAcquireMSISpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReleaseMSISpinLock routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

