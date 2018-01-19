---
UID: NF:storport.StorPortAcquireMSISpinLock
title: StorPortAcquireMSISpinLock function
author: windows-driver-content
description: The StorPortAcquireMSISpinLock routine acquires the message signaled interrupt (MSI) spin lock that is associated with the specified message.
old-location: storage\storportacquiremsispinlock.htm
old-project: storage
ms.assetid: 8aa5a8a6-2024-4b3e-a500-5a484d937a62
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortAcquireMSISpinLock
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
req.alt-api: StorPortAcquireMSISpinLock
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
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


### -param MessageID [in]

The identifier of the message whose spin lock the caller acquires.


### -param OldIrql [in]

A pointer to the storage for the original IRQL value to be used in a subsequent call to <a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a>.


## -returns
<b>StorPortAcquireMSISpinLock</b> returns one of the following values:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>Indicates that the spin lock was acquired successfully.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>HwDeviceExtension</i> was <b>NULL</b>.

 


## -remarks
A miniport driver calls the <b>StorPortAcquireMSISpinLock</b> routine to acquire the MSI spin lock for a particular message. To release the spin lock, the miniport driver calls the <a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a> routine. This routine is used by a miniport drivers to acquire a  the MSI spin lock for an individual message only when the <b>InterruptSynchronizationMode</b> member of the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure is set to <b>InterruptSynchronizePerMessage</b>.

When a miniport needs to synchronize with all messages, it can use one call to <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a> which will acquire a lock for each message in the proper order.


## -see-also
<dl>
<dt>
<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortAcquireMSISpinLock routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

