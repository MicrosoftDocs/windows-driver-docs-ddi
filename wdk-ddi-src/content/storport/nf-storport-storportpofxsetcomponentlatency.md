---
UID: NF:storport.StorPortPoFxSetComponentLatency
title: StorPortPoFxSetComponentLatency function
author: windows-driver-content
description: The StorPortPoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.
old-location: storage\storportpofxsetcomponentlatency.htm
old-project: storage
ms.assetid: F175ED42-3DB6-4568-96CA-EFC283B14887
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortPoFxSetComponentLatency, StorPortPoFxSetComponentLatency routine [Storage Devices], StorPortPoFxSetComponentLatency, storage.storportpofxsetcomponentlatency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortPoFxSetComponentLatency
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortPoFxSetComponentLatency function


## -description


The <b>StorPortPoFxSetComponentLatency</b> routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.


## -syntax


````
ULONG StorPortPoFxSetComponentLatency(
  _In_     PVOID         HwDeviceExtension,
  _In_opt_ PSTOR_ADDRESS Address,
  _In_     ULONG         Component,
  _In_     ULONGLONG     Latency
);
````


## -parameters




#### - HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a>.


#### - Address [in, optional]

The address of a storage device unit. This parameter is <b>NULL</b> when setting the latency of a storage adapter component.


#### - Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\storport\ns-storport-_stor_pofx_device.md">STOR_POFX_DEVICE</a> structure that the miniport driver registered for the device with a call to <a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a>. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


#### - Latency [in]

The time, in units of 100 nanoseconds, that the storage device component can tolerate  for a transition from an  idle state the active state.


## -returns


The <b>StorPortPoFxSetComponentLatency</b> routine returns one of these status codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The component latency successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Device</i> is NULL.

-or-

<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

-or-

The index in <i>Component</i> specifies a component greater than the component count for the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The storage device is  not registered with the  power management framework (PoFx).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
</table> 



## -see-also

<a href="..\wdm\nf-wdm-pofxsetcomponentlatency.md">PoFxSetComponentLatency</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPoFxSetComponentLatency routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

