---
UID: NF:storport.StorPortAcquireMSISpinLock
title: StorPortAcquireMSISpinLock function
author: windows-driver-content
description: The StorPortAcquireMSISpinLock routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message.
old-location: storage\storportacquiremsispinlock.htm
old-project: storage
ms.assetid: 8aa5a8a6-2024-4b3e-a500-5a484d937a62
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, I, L, M, P, S, StorPortAcquireMSISpinLock, StorPortAcquireMSISpinLock routine [Storage Devices], c, e, i, k, n, o, p, q, r, storage.storportacquiremsispinlock, storport/StorPortAcquireMSISpinLock, storprt_0db1ab5c-a2a5-4362-84e0-493a5cebc2d3.xml, t, u"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortAcquireMSISpinLock
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortAcquireMSISpinLock function


## -description


The <b>StorPortAcquireMSISpinLock</b> routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message. 


## -syntax


````
ULONG StorPortAcquireMSISpinLock(
  _In_ PVOID  HwDeviceExtension,
  _In_ ULONG  MessageID,
  _In_ PULONG OldIrql
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param MessageId

TBD


### -param OldIrql [in]

A pointer to the storage for the original IRQL value to be used in a subsequent call to <a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a>.


#### - MessageID [in]

The identifier of the message whose spin lock the caller acquires.


## -returns



<b>StorPortAcquireMSISpinLock</b> returns one of the following values:

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
Indicates that the spin lock was acquired successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



A miniport driver calls the <b>StorPortAcquireMSISpinLock</b> routine to acquire the MSI spin lock for a particular message. To release the spin lock, the miniport driver calls the <a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a> routine. This routine is used by a miniport drivers to acquire a  the MSI spin lock for an individual message only when the <b>InterruptSynchronizationMode</b> member of the <a href="..\storport\ns-storport-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure is set to <b>InterruptSynchronizePerMessage</b>.

When a miniport needs to synchronize with all messages, it can use one call to <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a> which will acquire a lock for each message in the proper order.




## -see-also

<a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a>



<a href="..\storport\ns-storport-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>



<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortAcquireMSISpinLock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

